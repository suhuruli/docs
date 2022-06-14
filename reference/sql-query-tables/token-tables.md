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

| Table Name                    | Description                                            |
| ----------------------------- | ------------------------------------------------------ |
| `eth.tokens`                  | ERC-20, ERC-721 and ERC-1155 token contracts           |
| `eth.token_transfers`         | ERC-20, ERC-721, and ERC-1155 token transfers          |
| `eth.recent_token_transfers`  | Token transfers from the last 30 minutes, \~128 blocks |
| `eth.tokens_erc20`            | ERC-20 token contracts                                 |
| `eth.token_transfers_erc20`   | ERC-20 token transfers                                 |
| `eth.tokens_erc721`           | ERC-721 token contracts                                |
| `eth.token_transfers_erc721`  | ERC-721 token transfers (NFTs)                         |
| `eth.tokens_erc1155`          | ERC-1155 token contracts                               |
| `eth.token_transfers_erc1155` | ERC-1155 token transfers                               |
| `eth.token_mints`             | ERC-20, ERC-721, and ERC-1155 token mints              |
| `eth.recent_token_mints`      | Token mints from the last 30 minutes, \~128 blocks     |

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
