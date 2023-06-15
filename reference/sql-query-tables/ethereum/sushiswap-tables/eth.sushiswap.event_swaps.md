---
description: >-
  SQL table schema for eth.sushiswap.event_swaps and
  eth.sushiswap.recent_event_swaps
---

# eth.sushiswap.event\_swaps

Ethereum Sushiswap swap events.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `address`          | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `amount0_in`       | CHARACTER VARYING |
| `amount1_in`       | CHARACTER VARYING |
| `amount0_out`      | CHARACTER VARYING |
| `amount1_out`      | CHARACTER VARYING |
| `sender`           | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
