---
description: SQL table schema for eth.beacon.withdrawals and eth.beacon.recent_withdrawals
---

# eth.beacon.withdrawals



| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `block_slot`       | DOUBLE            |
| `block_root`       | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `withdrawal_index` | DOUBLE            |
| `validator_index`  | DOUBLE            |
| `address`          | CHARACTER VARYING |
| `amount`           | DOUBLE            |
