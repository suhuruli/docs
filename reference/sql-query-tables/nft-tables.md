# NFT Tables

#### NFT specific tables

| Table Name                         | Description                                                                                                                   |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `eth.nft_contracts`                | erc721 contracts                                                                                                              |
| `eth.nft_transfers`                | Transfers of erc721 tokens                                                                                                    |
| `eth.nft_owners`                   | Tracks the current owner of an NFT.                                                                                           |
| `eth.recent_nft_transfers`         | Transfers of erc721 tokens from the last 30 minutes, \~128 blocks                                                             |
| `eth.nft_transfers_hold_time`      | Adds an additional column to the nft\_transfers table that tracks how long the NFT was held for before the transfer occurred. |
| `eth.nft_airdrop_transfers`        | Airdrops of erc721 tokens                                                                                                     |
| `eth.recent_nft_airdrop_transfers` | Airdrops of erc721 tokens from the last 30 minutes, \~128 blocks                                                              |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE eth.nft_contracts;
DESCRIBE eth.nft_transfers;
DESCRIBE eth.nft_owners;
DESCRIBE eth.recent_nft_transfers;
DESCRIBE eth.nft_transfers_hold_time;
DESCRIBE eth.nft_airdrop_transfers;
DESCRIBE eth.recent_nft_airdrop_transfers;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name                                          | Indexed Columns                                                                            |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| `eth.nft_transfers` & `eth.nft_transfers_hold_time` | `block_number` `block_timestamp` `from_address` `to_address` `token_address`               |
| `eth.nft_airdrop_transfers`                         | `token_address` `token_id` `block_number` `block_timestamp` `symbol` `name` `from_address` |

