---
description: Ethereum token specific tables (preview)
---

# Token Tables

**Links**

* [Ethereum Token Standards](https://ethereum.org/en/developers/docs/standards/tokens/)
* [ERC-20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) Fungible tokens
* [ERC-721](https://ethereum.org/en/developers/docs/standards/tokens/erc-721/) NFTs
* [ERC-1155](https://ethereum.org/en/developers/docs/standards/tokens/erc-1155/) Multi-Token Standard

#### Token specific tables

| Table Name                    | Description                                            |
| ----------------------------- | ------------------------------------------------------ |
| `preview.eth.tokens`          | ERC-20, ERC-721 and ERC-1155 token contracts           |
| `preview.eth.tokens_erc20`    | ERC-20 token contracts                                 |
| `preview.eth.tokens_erc721`   | ERC-721 token contracts                                |
| `preview.eth.tokens_erc1155`  | ERC-1155 token contracts                               |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE preview.eth.tokens;
DESCRIBE preview.eth.tokens_erc20;
DESCRIBE preview.eth.tokens_erc721;
DESCRIBE preview.eth.tokens_erc1155;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name                    | Indexed Columns                                                  |
| ----------------------------- | ---------------------------------------------------------------- |
| `preview.eth.tokens`          | `block_number` `block_timestamp` `name` `symbol`                 |
| `preview.eth.tokens_erc20`    | `block_number` `block_timestamp` `name` `symbol`                 |
| `preview.eth.tokens_erc721`   | `block_number` `block_timestamp` `name` `symbol`                 |
| `preview.eth.tokens_erc1155`  | `block_number` `block_timestamp` `name` `symbol`                 |
