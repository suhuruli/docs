---
description: SQL table schema for polygon.tokens_erc20
---

# polygon.tokens\_erc20

Polygon ERC-20 token contracts.

| Column Name       | Data Type         | Description                                 |
| ----------------- | ----------------- | ------------------------------------------- |
| `address`         | CHARACTER VARYING | Address of the token                        |
| `name`            | CHARACTER VARYING | Name of the token                           |
| `symbol`          | CHARACTER VARYING | Symbol of the token                         |
| `decimals`        | INTEGER           | The number of decimals the token uses       |
| `total_supply`    | CHARACTER VARYING | Total supply of the token                   |
| `block_number`    | BIGINT            | Block number where the token was created    |
| `block_timestamp` | BIGINT            | Block timestamp where the token was created |
| `block_hash`      | CHARACTER VARYING | Block hash where the token was created      |
