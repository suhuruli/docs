---
description: SQL table schema for goerli.token_transfers_erc1155
---

# goerli.token\_transfers\_erc1155

Goerli ERC-1155 token transfers.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `token_address`    | CHARACTER VARYING |
| `operator`         | CHARACTER VARYING |
| `from_address`     | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `token_id`         | CHARACTER VARYING |
| `value`            | CHARACTER VARYING |
| `value_hex`        | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
| `batch_index`      | BIGINT            |
