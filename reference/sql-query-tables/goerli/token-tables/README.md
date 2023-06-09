---
description: Goerli Token tables available to query via SQL
---

# Token Tables

**Links**

* [Ethereum Token Standards](https://ethereum.org/en/developers/docs/standards/tokens/)
* [ERC-20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) Fungible tokens
* [ERC-721](https://ethereum.org/en/developers/docs/standards/tokens/erc-721/) NFTs
* [ERC-1155](https://ethereum.org/en/developers/docs/standards/tokens/erc-1155/) Multi-Token Standard

#### Token specific tables

| Table Name                                                                    | Description                                            |
| ----------------------------------------------------------------------------- | ------------------------------------------------------ |
| [`goerli.tokens`](goerli.tokens.md)                                           | ERC-20, ERC-721 and ERC-1155 token contracts           |
| [`goerli.token_transfers`](goerli.token\_transfers.md)                        | ERC-20, ERC-721, and ERC-1155 token transfers          |
| [`goerli.recent_token_transfers`](goerli.token\_transfers.md)                 | Token transfers from the last 30 minutes, \~128 blocks |
| [`goerli.tokens_erc20`](goerli.tokens\_erc20.md)                              | ERC-20 token contracts                                 |
| [`goerli.token_transfers_erc20`](goerli.token\_transfers\_erc20.md)           | ERC-20 token transfers                                 |
| [`goerli.tokens_erc721`](goerli.tokens\_erc721.md)                            | ERC-721 token contracts                                |
| [`goerli.token_transfers_erc721`](goerli.token\_transfers\_erc20.md)          | ERC-721 token transfers (NFTs)                         |
| [`goerli.tokens_erc1155`](../../ethereum/token-tables/eth.tokens\_erc1155.md) | ERC-1155 token contracts                               |
| [`goerli.token_transfers_erc1155`](goerli.token\_transfers\_erc1155.md)       | ERC-1155 token transfers                               |
| [`goerli.token_mints`](goerli.token\_mints.md)                                | ERC-20, ERC-721, and ERC-1155 token mints              |
| [`goerli.recent_token_mints`](goerli.token\_mints.md)                         | Token mints from the last 30 minutes, \~128 blocks     |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE goerli.tokens;
DESCRIBE goerli.token_transfers;
DESCRIBE goerli.tokens_erc20;
DESCRIBE goerli.token_transfers_erc20;
DESCRIBE goerli.tokens_erc721;
DESCRIBE goerli.token_transfers_erc721;
DESCRIBE goerli.tokens_erc1155;
DESCRIBE goerli.token_transfers_erc1155;
DESCRIBE goerli.token_mints;
DESCRIBE goerli.recent_token_mints;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name                       | Indexed Columns                                                  |
| -------------------------------- | ---------------------------------------------------------------- |
| `goerli.tokens`                  | `block_number` `block_timestamp` `name` `symbol`                 |
| `goerli.tokens_erc20`            | `block_number` `block_timestamp` `name` `symbol`                 |
| `goerli.tokens_erc721`           | `block_number` `block_timestamp` `name` `symbol`                 |
| `goerli.tokens_erc1155`          | `block_number` `block_timestamp` `name` `symbol`                 |
| `goerli.token_transfers`         | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `goerli.recent_token_transfers`  | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `goerli.token_transfers_erc20`   | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `goerli.token_transfers_erc721`  | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `goerli.token_transfers_erc1155` | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `goerli.token_mints`             | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
| `goerli.recent_token_mints`      | `block_number` `block_timestamp` `block_hash` `transaction_hash` |
