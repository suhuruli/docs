---
description: A tutorial for using prices data for asset transfer valuations
---

# Asset Transfer Valuations

Author: [**Mitch Devenport**](https://twitter.com/mitch\_devenport?s=21\&t=qnvMA1VlJmTfPmkD-T3pmQ)

_Estimated time to complete: \~5 minutes_

## Overview

Spice offers historical, high-low-open-close (HLOC) prices data for [thousands of cryptocurrency and fiat pairs](../reference/sql-query-tables/prices/), accessible via SQL Query and REST APIs.

In this tutorial, we'll explore how we can combine Spice prices data with asset transfer data to determine the value of a transfer converted to fiat (or another cryptocurrency) _at the time the transfer was made_.

## The Good Stuff

Let's hop right in. We'll get our feet wet by running query to get the value of ETH in USD at a specific point in time:

```sql
SELECT * FROM prices.eth_usd WHERE "timestamp" = '2017-09-20 12:34'
```

This query will return the high, low, opening, and closing (HLOC) price of ETH converted to USD on September 20th, 2017 from 12:34:00 PM to 12:34:59 PM. Note, we must double-quote the word `timestamp` as it is a reserved keyword.

<table><thead><tr><th width="187">timestamp</th><th width="141">high</th><th width="147">low</th><th>open</th><th>close</th></tr></thead><tbody><tr><td>2017-09-20 12:34</td><td>286.33</td><td>286.32</td><td>286.33</td><td>286.33</td></tr></tbody></table>

The result of this query makes it abundantly clear that I should've bought ETH on September 20th, 2017 between 12:34:00 PM and 12:34:59 PM. Unfortunately, I was already well aware of that, so let's introduce the Spice `eth.asset_transfers` dataset to learn something we didn't already know.

Let's suppose I was smart and that I did purchase ETH at this time; now I want to know exactly how much that purchase has grown in USD. We'll assume I already know the transaction hash of the transfer, so I can use that to look up the value of ETH in USD at the time of the transfer:

```sql
SELECT 
    transfers.amount as amount_eth, 
    transfers.amount * prices."close" AS amount_usd 
FROM (
    SELECT amount FROM eth.asset_transfers 
    WHERE transaction_hash = '0x41094b61052d60ba5e7ff3a12fea7ab87eacf491c2380d5d9507625cb419f89b'
) AS transfers
LEFT JOIN (
    SELECT "close" FROM prices.eth_usd WHERE "timestamp" = '2017-09-20 12:34'
) AS prices
ON true
```

The query will return the amount of the transfer both in ETH and USD at that moment in time!

| amount\_eth | amount\_usd |
| ----------- | ----------- |
| 3200.00     | 916256.00   |

If you happen to know the real buyer here, tell them congratulations on being rich for me. If you happen to know the seller, then put me in touch so I can forward along the details of my support group.

Now, let's say we only know our wallet address and we want to find the USD value of all ETH transactions we've ever made:

```sql
SELECT 
    transfers."timestamp", 
    transfers.amount AS amount_eth, 
    transfers.amount * prices."close" AS amount_usd 
FROM (
    SELECT 
        amount,
        date_trunc('minute', to_timestamp(block_timestamp)) AS "timestamp"
    FROM eth.asset_transfers   
    WHERE 
        symbol = 'eth' AND 
        (from_address = '0xf2be95116845252a28bd43661651917dc183dab1' OR 
        to_address = '0xf2be95116845252a28bd43661651917dc183dab1')
) AS transfers
LEFT JOIN 
(SELECT "timestamp", "close" FROM prices.eth_usd) AS prices
ON transfers."timestamp" = prices."timestamp"
```

<figure><img src="../.gitbook/assets/Screenshot 2023-09-15 at 5.43.51 PM.png" alt=""><figcaption><p>Value in USD of all transactions to and from a wallet address</p></figcaption></figure>

I'll spare you the full output here, but as you can see we have a USD value for every ETH transfer we've ever made using this wallet address. This could easily be split into deposits (i.e. our address is the `to_address`) and withdrawals (i.e. our address is the `from_address`) to create a ledger.

Let's take things a step further and say we want to get value of all transfers to/from this wallet, not just our ETH transfers:

```sql
SELECT 
    transfers."timestamp", 
    transfers.pair, 
    transfers.amount AS amount_base, 
    transfers.amount * prices."close" AS amount_usd 
FROM (
    SELECT 
        concat(upper(symbol), '-USD') as pair, 
        amount,
        date_trunc('minute', to_timestamp(block_timestamp)) AS "timestamp"
    FROM eth.asset_transfers   
    WHERE 
        from_address = '0xf2be95116845252a28bd43661651917dc183dab1' 
        OR to_address = '0xf2be95116845252a28bd43661651917dc183dab1'
) AS transfers
LEFT JOIN 
(SELECT "timestamp", "close", pair FROM prices.all_pairs) AS prices
ON transfers.pair = prices.pair AND transfers."timestamp" = prices."timestamp"
```

Note here that we are using `prices.all_pairs` which contains all historical prices for all pairs tracked by Spice. This table is really useful for use cases where pairs are determined dynamically at runtime, such as the case above, but as a performance consideration we recommend using the pair specific tables (e.g. `prices.eth_usd`) if your pairs are statically known at compile time.

Now we're really talking! We have a complete list of every asset transfer we've ever made with its value in USD at that point in time. We could easily extend this query to multiple wallet addresses to create a comprehensive ledger of all our transactions and holdings! We also don't have to stop at just USD, we could use the same logic to get values in other fiats like GBP or even other cryptocurrency like BTC!

## Conclusion

Congratulations on making it this far! 🎉

You now have an idea of the powerful information available to you by augmenting Spice datasets with Spice [prices data](../reference/sql-query-tables/prices/).

Let us know what cool insights you find on [Discord](https://discord.gg/PUCapX22En).
