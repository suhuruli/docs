---
description: SQL table schema for eth.withdrawals and eth.recent_withdrawals
---

# eth.withdrawals

Ethereum Block withdrawals.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `withdrawal_index` | DOUBLE            |
| `validator_index`  | DOUBLE            |
| `amount`           | DOUBLE            |
| `address`          | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
| `block_number`     | BIGINT            |
