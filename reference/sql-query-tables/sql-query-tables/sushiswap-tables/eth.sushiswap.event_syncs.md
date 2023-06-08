---
description: >-
  SQL table schema for eth.sushiswap.event_syncs and
  eth.sushiswap.recent_event_syncs
---

# eth.sushiswap.event\_syncs

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `address`          | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `reserve0`         | CHARACTER VARYING |
| `reserve1`         | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
