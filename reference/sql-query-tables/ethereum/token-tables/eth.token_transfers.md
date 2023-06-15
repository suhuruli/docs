---
description: SQL table schema for eth.token_transfers
---

# eth.token\_transfers

Ethereum Token tables ERC-20, ERC-721, and ERC-1155 token transfers.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `token_address`    | CHARACTER VARYING |
| `operator`         | CHARACTER VARYING |
| `from_address`     | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `token_id`         | CHARACTER VARYING |
| `value`            | CHARACTER VARYING |
| `value_hex`        | CHARACTER VARYING |
| `token_standard`   | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
| `batch_index`      | BIGINT            |
