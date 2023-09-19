---
description: SQL table schema for polygon.tokens_erc1155
---

# polygon.tokens\_erc1155

Polygon ERC-1155 token contracts.

| Column Name       | Data Type         | Description                                 |
| ----------------- | ----------------- | ------------------------------------------- |
| `address`         | CHARACTER VARYING | Address of the token                        |
| `name`            | CHARACTER VARYING | Name of the token                           |
| `symbol`          | CHARACTER VARYING | Symbol of the token                         |
| `block_number`    | BIGINT            | Block number where the token was created    |
| `block_timestamp` | BIGINT            | Block timestamp where the token was created |
| `block_hash`      | CHARACTER VARYING | Block hash where the token was created      |
