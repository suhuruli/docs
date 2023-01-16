# Token Tables

**Links**

* [Ethereum Token Standards](https://ethereum.org/en/developers/docs/standards/tokens/)
* [ERC-20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) Fungible tokens
* [ERC-721](https://ethereum.org/en/developers/docs/standards/tokens/erc-721/) NFTs
* [ERC-1155](https://ethereum.org/en/developers/docs/standards/tokens/erc-1155/) Multi-Token Standard

#### Polygon Token specific tables

| Table Name                        | Description                                            |
| --------------------------------- | ------------------------------------------------------ |
| `polygon.tokens`                  | ERC-20, ERC-721 and ERC-1155 token contracts           |
| `polygon.token_transfers`         | ERC-20, ERC-721, and ERC-1155 token transfers          |
| `polygon.recent_token_transfers`  | Token transfers from the last 30 minutes, \~128 blocks |
| `polygon.tokens_erc20`            | ERC-20 token contracts                                 |
| `polygon.token_transfers_erc20`   | ERC-20 token transfers                                 |
| `polygon.tokens_erc721`           | ERC-721 token contracts                                |
| `polygon.token_transfers_erc721`  | ERC-721 token transfers (NFTs)                         |
| `polygon.tokens_erc1155`          | ERC-1155 token contracts                               |
| `polygon.token_transfers_erc1155` | ERC-1155 token transfers                               |
| `polygon.token_mints`             | ERC-20, ERC-721, and ERC-1155 token mints              |
| `polygon.recent_token_mints`      | Token mints from the last 30 minutes, \~128 blocks     |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE polygon.tokens;
DESCRIBE polygon.token_transfers;
DESCRIBE polygon.tokens_erc20;
DESCRIBE polygon.token_transfers_erc20;
DESCRIBE polygon.tokens_erc721;
DESCRIBE polygon.token_transfers_erc721;
DESCRIBE polygon.tokens_erc1155;
DESCRIBE polygon.token_transfers_erc1155;
DESCRIBE polygon.token_mints;
DESCRIBE polygon.recent_token_mints;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name                | Indexed Columns                                                                                 |
| ------------------------- | ----------------------------------------------------------------------------------------------- |
| `polygon.token_transfers` | `block_number` `block_timestamp` `transaction_hash` `token_address` `from_address` `to_address` |
