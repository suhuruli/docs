---
description: SQL table schema for btc.transaction_outputs
---

# btc.transaction\_outputs

All Bitcoin outputs from transactions.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `transaction_hash` | CHARACTER VARYING |
| `index`            | BIGINT            |
| `script_asm`       | CHARACTER VARYING |
| `script_hex`       | CHARACTER VARYING |
| `type`             | CHARACTER VARYING |
| `addresses`        | ANY               |
| `value`            | DECIMAL           |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
