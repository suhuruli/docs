---
description: Ethereum token specific tables
---

# Token Tables

**Links**

* [Ethereum Token Standards](https://ethereum.org/en/developers/docs/standards/tokens/)
* [ERC-20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) Fungible tokens
* [ERC-721](https://ethereum.org/en/developers/docs/standards/tokens/erc-721/) NFTs
* [ERC-1155](https://ethereum.org/en/developers/docs/standards/tokens/erc-1155/) Multi-Token Standard

#### Token specific tables

| Table Name                    | Description                       |
| ----------------------------- | --------------------------------- |
| `eth.tokens_erc20`            | erc20 token contracts             |
| `eth.token_transfers_erc20`   | Transfers of erc20 tokens         |
| `eth.tokens_erc721`           | erc721 token contracts            |
| `eth.token_transfers_erc721`  | Transfers of erc721 tokens (NFTs) |
| `eth.tokens_erc1155`          | erc1155 token contracts           |
| `eth.token_transfers_erc1155` | Transfer of erc1155 tokens        |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE eth.tokens_erc20;
DESCRIBE eth.token_transfers_erc20;
DESCRIBE eth.tokens_erc721;
DESCRIBE eth.token_transfers_erc721;
DESCRIBE eth.tokens_erc1155;
DESCRIBE eth.token_transfers_erc1155;
```
