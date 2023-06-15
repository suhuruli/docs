---
description: SQL table schema for polygon.token_transfers_erc721
---

# polygon.token\_transfers\_erc721

Polygon ERC-721 token transfers (NFTs).

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `token_address`    | CHARACTER VARYING |
| `from_address`     | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `token_id`         | CHARACTER VARYING |
| `value`            | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
