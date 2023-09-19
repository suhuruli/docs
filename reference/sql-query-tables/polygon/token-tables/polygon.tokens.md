---
description: SQL table schema for polygon.tokens
---

# polygon.tokens

Polygon ERC-20, ERC-721 and ERC-1155 token contracts.

| Column Name       | Data Type         | Description                                 |
| ----------------- | ----------------- | ------------------------------------------- |
| `address`         | CHARACTER VARYING | Address of the token                        |
| `name`            | CHARACTER VARYING | Name of the token                           |
| `symbol`          | CHARACTER VARYING | Symbol of the token                         |
| `decimals`        | INTEGER           | The number of decimals the token uses       |
| `total_supply`    | CHARACTER VARYING | Total supply of the token                   |
| `is_erc20`        | BOOLEAN           | Whether the token is ERC20 token or not     |
| `is_erc721`       | BOOLEAN           | Whether the token is ERC721 token or not    |
| `is_erc1155`      | BOOLEAN           | Whether the token is ERC1155 token or not   |
| `block_number`    | BIGINT            | Block number where the token was created    |
| `block_timestamp` | BIGINT            | Block timestamp where the token was created |
| `block_hash`      | CHARACTER VARYING | Block hash where the token was created      |
