---
description: Polygon NFT tables available to query via SQL
---

# NFT Tables

#### Polygon NFT specific tables

| Table Name                                                                   | Description                                                                                                                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`polygon.nfts`](polygon.nfts.md)                                            | All NFTs from both ERC721 and ERC1155 contracts.                                                                                                                             |
| [`polygon.nft_contracts`](polygon.nft\_contracts.md)                         | All erc721 contracts & subset of erc1155 contracts that contain NFTs.                                                                                                        |
| [`polygon.nft_transfers`](polygon.nft\_transfers.md)                         | <p>Transfers of erc721 &#x26; erc1155 NFTs.</p><p>Does not include fungible tokens from erc1155 contracts.</p>                                                               |
| [`polygon.nft_owners`](polygon.nft\_owners.md)                               | <p>Tracks the current owner of an NFT.<br>This table is mutable; the number of rows within a given time or block range can be different due to changes in NFT ownership.</p> |
| [`polygon.recent_nft_transfers`](polygon.nft\_transfers.md)                  | Transfers of NFTs from the last 30 minutes, \~128 blocks                                                                                                                     |
| [`polygon.nft_airdrop_transfers`](polygon.nft\_airdrop\_transfers.md)        | Airdrops of NFTs                                                                                                                                                             |
| [`polygon.recent_nft_airdrop_transfers`](polygon.nft\_airdrop\_transfers.md) | Airdrops of NFTs from the last 30 minutes, \~128 blocks                                                                                                                      |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE polygon.nfts;
DESCRIBE polygon.nft_contracts;
DESCRIBE polygon.nft_transfers;
DESCRIBE polygon.nft_owners;
DESCRIBE polygon.recent_nft_transfers;
DESCRIBE polygon.nft_airdrop_transfers;
DESCRIBE polygon.recent_nft_airdrop_transfers;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name                             | Indexed Columns                                      |
| -------------------------------------- | ---------------------------------------------------- |
| `polygon.nft_transfers`                | `block_number`                                       |
| `polygon.nft_airdrop_transfers`        | `block_number`                                       |
| `polygon.nfts`                         |                                                      |
| `polygon.nft_contracts`                | `address`                                            |
| `polygon.nft_owners`                   | `token_address` `token_id` `owner` `block_timestamp` |
| `polygon.recent_nft_transfers`         |                                                      |
| `polygon.recent_nft_airdrop_transfers` |                                                      |
