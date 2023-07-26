---
description: SQL table schema for polygon.token_mints and polygon.recent_token_mints
---

# polygon.token\_mints

Polygon ERC-20, ERC-721, and ERC-1155 token mints.

| Column Name        | Data Type         | Description                             |
| ------------------ | ----------------- | --------------------------------------- |
| `name`             | CHARACTER VARYING | Name of the minted token                |
| `symbol`           | CHARACTER VARYING | Symbol of the minted token              |
| `token_address`    | CHARACTER VARYING | Address of the minted token             |
| `to_address`       | CHARACTER VARYING | Recipient address of the minted token   |
| `value`            | CHARACTER VARYING | Amount of token minted                  |
| `transaction_hash` | CHARACTER VARYING | Transaction hash                        |
| `block_number`     | BIGINT            | Block number where token mint was in    |
| `block_timestamp`  | BIGINT            | Block timestamp where token mint was in |
