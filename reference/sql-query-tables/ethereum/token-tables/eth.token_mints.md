---
description: SQL table schema for eth.token_mints and eth.recent_token_mints
---

# eth.token\_mints

Ethereum Token mints from the last 30 minutes, \~128 blocks.

| Colum Name         | Data Type         |
| ------------------ | ----------------- |
| `name`             | CHARACTER VARYING |
| `symbol`           | CHARACTER VARYING |
| `token_address`    | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `value`            | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `block_number`     | BIGINT            |
| `block_timestamp`  | BIGINT            |
