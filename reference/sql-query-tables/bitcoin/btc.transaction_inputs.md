---
description: SQL table schema for btc.transaction_inputs and btc.recent_transaction_inputs
---

# btc.transaction\_inputs

| Column Name              | Data Type         |
| ------------------------ | ----------------- |
| `transaction_hash`       | CHARACTER VARYING |
| `index`                  | BIGINT            |
| `spent_transaction_hash` | CHARACTER VARYING |
| `spent_output_index`     | BIGINT            |
| `script_asm`             | CHARACTER VARYING |
| `script_hex`             | CHARACTER VARYING |
| `sequence`               | BIGINT            |
| `addresses`              | ANY               |
| `value`                  | DECIMAL           |
| `block_number`           | BIGINT            |
| `block_hash`             | CHARACTER VARYING |
| `block_timestamp`        | BIGINT            |
