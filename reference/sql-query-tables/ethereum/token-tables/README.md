---
description: Ethereum Token tables available to query via SQL
---

# Token Tables

**Links**

* [Ethereum Token Standards](https://ethereum.org/en/developers/docs/standards/tokens/)
* [ERC-20 Fungible tokens](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/)
* [ERC-721 NFTs](https://ethereum.org/en/developers/docs/standards/tokens/erc-721/)
* [ERC-1155 Multi-Token Standard](https://ethereum.org/en/developers/docs/standards/tokens/erc-1155/)

#### Token specific tables

| Table Name                                                        | Description                                            |
| ----------------------------------------------------------------- | ------------------------------------------------------ |
| [`eth.tokens`](eth.tokens.md)                                     | ERC-20, ERC-721 and ERC-1155 token contracts           |
| [`eth.token_transfers`](eth.token\_transfers.md)                  | ERC-20, ERC-721, and ERC-1155 token transfers          |
| [`eth.recent_token_transfers`](eth.recent\_token\_transfers.md)   | Token transfers from the last 30 minutes, \~128 blocks |
| [`eth.tokens_erc20`](eth.tokens\_erc20.md)                        | ERC-20 token contracts                                 |
| [`eth.token_transfers_erc20`](eth.token\_transfers\_erc20.md)     | ERC-20 token transfers                                 |
| [`eth.tokens_erc721`](eth.tokens\_erc721.md)                      | ERC-721 token contracts                                |
| [`eth.token_transfers_erc721`](eth.token\_transfers\_erc721.md)   | ERC-721 token transfers (NFTs)                         |
| [`eth.tokens_erc1155`](eth.tokens\_erc1155.md)                    | ERC-1155 token contracts                               |
| [`eth.token_transfers_erc1155`](eth.token\_transfers\_erc1155.md) | ERC-1155 token transfers                               |
| [`eth.token_mints`](eth.token\_mints.md)                          | ERC-20, ERC-721, and ERC-1155 token mints              |
| [`eth.recent_token_mints`](eth.token\_mints.md)                   | Token mints from the last 30 minutes, \~128 blocks     |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE eth.tokens;
DESCRIBE eth.token_transfers;
DESCRIBE eth.tokens_erc20;
DESCRIBE eth.token_transfers_erc20;
DESCRIBE eth.tokens_erc721;
DESCRIBE eth.token_transfers_erc721;
DESCRIBE eth.tokens_erc1155;
DESCRIBE eth.token_transfers_erc1155;
DESCRIBE eth.token_mints;
DESCRIBE eth.recent_token_mints;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name                    | Indexed Columns                                                  |
| ----------------------------- | ---------------------------------------------------------------- |
| `eth.tokens`                  | `block_number` `block_timestamp` `name` `symbol`                 |
| `eth.tokens_erc20`            | `block_number` `block_timestamp` `name` `symbol`                 |
| `eth.tokens_erc721`           | `block_number` `block_timestamp` `name` `symbol`                 |
| `eth.tokens_erc1155`          | `block_number` `block_timestamp` `name` `symbol`                 |
| `eth.token_transfers`         | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `eth.recent_token_transfers`  | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `eth.token_transfers_erc20`   | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `eth.token_transfers_erc721`  | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `eth.token_transfers_erc1155` | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `eth.token_mints`             | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `eth.recent_token_mints`      | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
