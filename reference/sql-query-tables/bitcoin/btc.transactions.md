---
description: SQL table schema for btc.transactions and btc.recent_transactions
---

# btc.transactions

Bitcoin Block transactions.

| Column Name       | Data Type         |
| ----------------- | ----------------- |
| `hash`            | CHARACTER VARYING |
| `size`            | BIGINT            |
| `virtual_size`    | BIGINT            |
| `version`         | BIGINT            |
| `lock_time`       | BIGINT            |
| `block_hash`      | CHARACTER VARYING |
| `block_number`    | BIGINT            |
| `block_timestamp` | BIGINT            |
| `input_count`     | BIGINT            |
| `output_count`    | BIGINT            |
| `input_value`     | DECIMAL           |
| `output_value`    | DECIMAL           |
| `is_coinbase`     | BOOLEAN           |
| `fee`             | DECIMAL           |
