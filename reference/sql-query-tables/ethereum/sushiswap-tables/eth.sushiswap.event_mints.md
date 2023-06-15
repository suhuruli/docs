---
description: >-
  SQL table schema for eth.sushiswap.event_mints and
  eth.sushiswap.recent_event_mints
---

# eth.sushiswap.event\_mints

Ethereum Sushiswap mint events.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `address`          | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `amount0`          | CHARACTER VARYING |
| `amount1`          | CHARACTER VARYING |
| `sender`           | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
