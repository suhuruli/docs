# NFT Tables

#### NFT specific tables

| `eth.nft_contracts`         | erc721 contracts           |
| --------------------------- | -------------------------- |
| `eth.nft_transfers`         | Transfers of erc721 tokens |
| `eth.nft_airdrop_transfers` | Airdrops of erc721 tokens  |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES
```

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE eth.nft_contracts;
DESCRIBE eth.nft_transfers;
DESCRIBE eth.nft_airdrop_transfers;
```
