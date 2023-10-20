---
description: A tutorial for working with Ethereum token and NFT data.
---

# Tokens & NFTs

_Estimated time to complete: \~10 minutes_

## Overview

Spice makes it easy to use bulk Ethereum token and NFT data. Traditional RESTful APIs usually limit results to 100s per page. Spice supports the high-performance, vectorized binary format [Apache Arrow](../api/sql-query/apache-arrow-flight-api.md) that enables retrieving millions of rows in a single request.

Spice has automated, on-chain token detection for ERC-20, ERC-721, and ERC-1155 tokens generating [token-specific](https://docs.spice.ai/reference/sql-query-tables/token-tables) and [NFT](https://docs.spice.ai/reference/sql-query-tables/nft-tables) datasets in real-time.

In this tutorial, we'll explore how to use these datasets to answer the following questions:

* How many NFTs exist? How many of them are ERC-721 NFTs vs ERC-1155 NFTs?
* Which ERC-721 contracts had the most token mints in the last 30 minutes?
* Which contracts had the most NFT transfers in March 2021, the month the largest NFT transfer by value took place?
* Who are the current owners of all Ethereum NFTs?
* Using the standards compliance confidence for a specific application.

## Tokens and NFTs

While any smart contract can technically create a "token," the [Ethereum Foundation](https://ethereum.org/en/) publishes a set of common [Token Standards](https://ethereum.org/en/developers/docs/standards/tokens), which help ensure composability and compatibility with other smart contracts.

Let's explore tokens and contracts and their Spice datasets before jumping into the questions.

### Tokens vs Contracts

The words tokens and contracts are often used interchangeably but according to the Ethereum Foundation they have specific definitions. A **contract** (or smart contract) is a program that runs on the Ethereum blockchain. It's a collection of code (its functions) and data (its state) that resides at a specific address on the Ethereum blockchain. A **token** is a crypto asset that can be utilized on blockchain ecosystems for economic, governance, or other purposes. A token contract is the implementation of a token.

Some tokens have an entire contract dedicated to their implementation, as with ERC-20 tokens. Other contract implementations may include many different tokens, such as with the ERC-721 and ERC-1155 standards.

Spice supports the major token standards in use: ERC-20, ERC-721, and ERC-1155.

Spice uses the convention that a "token" refers to the "contract that implements a token standard". To refer to the logical tokens that exist as part of a contract we will use the term "nfts (non-fungible tokens)", "fungible tokens" or "token transfers". E.g. There is one [Bored Ape Yacht Club](https://opensea.io/collection/boredapeyachtclub) contract and many NFT tokens.

### Token Contracts Datasets

Datasets related to token contracts. I.e. The [Bored Ape Yacht Club](https://opensea.io/collection/boredapeyachtclub) contract appears only once in each dataset.

* `eth.contracts` - Deployed contracts with their bytecode, function sighashes, token standard detection status, and detection confidence.
* `eth.tokens` - Token contracts with their name, symbol, decimals, and total supply along with the status of each token standard.
  * `eth.tokens_erc20`, `eth.tokens_erc721`, `eth.tokens_erc1155` - Identical to `eth.tokens` but filtered to each token standard
* `eth.nft_contracts` - Similar to `eth.tokens` but filtered only to contracts that have at least one minted NFT.

### NFT & Token Transfer Datasets

Datasets related to individual NFTs and logical token transfers. I.e. All \~10,000 NFTs in the [Bored Ape Yacht Club](https://opensea.io/collection/boredapeyachtclub) collection are included, along with transfers, and the current owner of each.

* `eth.nfts` - NFTs and their token standard compliance status.
* `eth.nft_owners` - NFTs and their current owner.
* `eth.token_transfers` - Transfers of tokens including mints and burns.
  * `eth.recent_token_transfers` - The `token_transfers` dataset filtered to the last 30 minutes. Several Spice datasets have a corresponding `recent_` table that follows this pattern.
  * `eth.token_transfers_erc20`, `eth.token_transfers_erc721`, `eth.token_transfers_erc1155` - `token_transfers` filtered to each token standard.
* `eth.nft_transfers` - NFT transfers. A subset of `eth.token_transfers` filtered to all ERC-721 transfers and ERC-1155 transfers of NFTs.
  * `eth.recent_nft_transfers` - `nft_transfers` filtered to the last 30 minutes.

{% hint style="info" %}
The ERC-1155 token standard is a "multi-token" standard that can contain both NFTs and fungible tokens. The `eth.nft_` datasets refer to the subset of ERC-1155 tokens that are NFTs.
{% endhint %}

* `eth.nft_airdrop_transfers` - `nft_transfers` filtered to transfers where no ether was exchanged.
  * `eth.recent_nft_airdrop_transfers` - `nft_airdrop_transfers` filtered to the last 30 minutes.

## Questions

### How many NFTs exist? How many of them are ERC-721 NFTs vs ERC-1155 NFTs?

We can answer this question using `eth.nfts` by counting how many NFTs there are for each token standard and combining them:

```sql
SELECT
count(CASE WHEN is_erc721 is true THEN 1 END) as erc721s,
count(CASE WHEN is_erc1155 is true THEN 1 END) as erc1155s
FROM eth.nfts
```

![64 million ERC-721 NFTs and 1.1 million ERC-1155 NFTs](<../.gitbook/assets/Screen Shot 2022-06-22 at 9.14.28 AM.png>)

### Which ERC-721 contracts have the most token mints in the last 30 minutes?

Recent token mints can be determined by using the `eth.recent_token_transfers` filtered to ERC-721s where the `from_address` is the zero address. Counting the mints from distinct token addresses shows which contracts have recently minted tokens.

The `recent_` datasets are the fastest to query but if you need historical mints, use `eth.token_transfers_erc721` filtered to `block_timestamp`.

```sql
select token_address, count(token_address) as "num_mints"
from eth.recent_token_transfers
where token_standard = 'erc721' and from_address = '0x0000000000000000000000000000000000000000'
group by token_address
order by count(token_address) desc
```

![Recent ERC-721 token mints, notice how fast it is 🏎💨](<../.gitbook/assets/Screen Shot 2022-06-21 at 6.17.54 PM.png>)

If you were instead interested in all NFT mints (including ERC-1155), which table would you use instead?

If you guessed `eth.recent_nft_transfers`, you would be correct! You could also modify the query to add `where token_standard = 'erc721' or token_standard = 'erc1155'`, which would include fungible ERC-1155 token mints.

### Which contracts had the most NFT transfers in March 2021?

The `eth.nft_transfers` table is perfect for answering this question. The only potentially tricky part is filtering the data to the time period we're interested in. We've already seen above how to do an aggregation to group by contracts and display the counts.

On most datasets in Spice, there is a `block_timestamp` column that tracks when the data was emitted using the number of seconds since the Unix epoch. This is commonly referred to as [Unix time](https://en.wikipedia.org/wiki/Unix\_time). There is a SQL function `UNIX_TIMESTAMP()` that we can use to convert a human-readable date into a Unix timestamp.

```sql
select token_address, count(*) as "num_transfers" from eth.nft_transfers
where block_timestamp between UNIX_TIMESTAMP('2021-03-01 00:00:00') 
                          and UNIX_TIMESTAMP('2021-04-01 00:00:00')
group by token_address
order by count(*) desc
```

<figure><img src="../.gitbook/assets/Screen Shot 2022-09-08 at 2.58.53 PM.png" alt=""><figcaption><p>A month of NFT transfer data in less than 2 seconds</p></figcaption></figure>

### Who are the current owners of all \~60M+ NFTs?

It is possible to use Spice to get all \~60M owners of all NFTs that exist using the `eth.nft_owners` table. This can be useful for performing your own data science on the data in your own systems. The HTTP API that the Spice.ai portal uses is limited to 500 rows, so you will need to use one of the Spice SDKs ([Python](../sdks/python-sdk/), [Node.js](../sdks/node.js-sdk/)) to run the query and retrieve all of the results.

Spice also has a limitation of 90 seconds for a single query. To get all 60M owners, you will need to paginate through the data using a combination of `ORDER BY`, `LIMIT` and `OFFSET`. Here is an example:

```sql
SELECT * FROM eth.nft_owners 
ORDER BY token_address, token_id 
LIMIT 1000000 
OFFSET 0
```

![](<../.gitbook/assets/Screen Shot 2022-06-21 at 6.45.46 PM.png>)

How would you modify the above query to show which wallet owns the most NFTs?

Hopefully, you came up with something that looks like this:

```sql
SELECT owner, count(*) FROM eth.nft_owners
GROUP BY owner
ORDER BY count(*) DESC
LIMIT 10
```

![Unsurprisingly most NFTs are owned by the zero address, i.e. burned.](<../.gitbook/assets/Screen Shot 2022-06-21 at 6.49.47 PM.png>)

### Using the standards compliance confidence for a specific application

For most applications, it is sufficient to use the token or NFT-specific datasets, or the `is_erc` fields on `eth.contracts` such as `eth.erc_721`. Because token standards detection is a heuristic these datasets and fields determine token standards compliance using the Spice standards compliance confidence fields:

* `erc20_confidence`
* `erc721_confidence`
* `erc1155_confidence`

A contract is determined to be compliant if the confidence is greater than or equal to 0.9 (90%). The confidence starts at 0 and is raised as conditions of the standard are met. This inherently results in a detection time to accuracy trade-off where a contract might take time (blocks) before it is determined to meet the complete token standard.

Applications that require finer control over this detection time to accuracy trade-off can use the confidence fields directly. For example, if an application wanted to find any contracts or transfers that _might_ be an ERC-721 NFT, the application may query for any contract with a non-zero `erc721_confidence` field.

```sql
select address, erc20_confidence, erc721_confidence, erc1155_confidence from eth.contracts
where erc20_confidence > 0 or erc721_confidence > 0 or erc1155_confidence > 0
limit 100
```

![](<../.gitbook/assets/Screen Shot 2022-06-21 at 7.25.59 PM.png>)

## Conclusion

Congratulations on making it this far! 🎉

You now have an idea of how to use token & NFT data in Spice. We started by exploring what tokens and contracts are and the differences between them.

By using their datasets, we asked questions to some typical questions, and so with your new skills, you can start exploring the data with questions of your own.

Let us know what cool insights you find on [Discord](https://discord.gg/PUCapX22En).
