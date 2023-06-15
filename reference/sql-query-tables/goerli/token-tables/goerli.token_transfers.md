---
description: SQL table schema for goerli.token_transfers and goerli.recent_token_transfers
---

# goerli.token\_transfers

Goerli ERC-20, ERC-721, and ERC-1155 token transfers.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `token_address`    | CHARACTER VARYING |
| `from_address`     | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `token_id`         | CHARACTER VARYING |
| `token_standard`   | CHARACTER VARYING |
| `value`            | CHARACTER VARYING |
| `value_hex`        | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
| `batch_index`      | BIGINT            |
