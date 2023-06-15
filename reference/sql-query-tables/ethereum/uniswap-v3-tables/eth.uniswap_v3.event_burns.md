---
description: >-
  SQL table schema for eth.uniswap_v3.event_burns and
  eth.uniswap_v3.recent_event_burns
---

# eth.uniswap\_v3.event\_burns

Ethereum Uniswap-V3 burn events.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `address`          | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `tick_lower`       | INTEGER           |
| `tick_upper`       | INTEGER           |
| `amount`           | CHARACTER VARYING |
| `amount0`          | CHARACTER VARYING |
| `amount1`          | CHARACTER VARYING |
| `owner`            | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
