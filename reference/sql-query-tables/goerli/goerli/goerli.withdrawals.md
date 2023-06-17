---
description: SQL table schema for goerli.withdrawals and goerli.recent_withdrawals
---

# goerli.withdrawals

Goerli Block withdrawals.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `withdrawal_index` | DOUBLE            |
| `validator_index`  | DOUBLE            |
| `amount`           | DOUBLE            |
| `address`          | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
| `block_number`     | BIGINT            |
