---
description: >-
  SQL table schema for eth.sushiswap.event_burns and
  eth.sushiswap.recent_event_burns
---

# eth.sushiswap.event\_burns

Ethereum Sushiswap burn events.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `address`          | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `amount0`          | CHARACTER VARYING |
| `amount1`          | CHARACTER VARYING |
| `sender`           | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
