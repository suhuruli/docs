---
description: >-
  SQL table schema for eth.uniswap_v2.event_burns and
  eth.uniswap_v2.recent_event_burns
---

# eth.uniswap\_v2.event\_burns

Ethereum Uniswap-V2 burn events.

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
