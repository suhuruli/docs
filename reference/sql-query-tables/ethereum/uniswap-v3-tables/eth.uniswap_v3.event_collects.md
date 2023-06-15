---
description: >-
  SQL table schema for eth.uniswap_v3.event_collects and
  eth.uniswap_v3.recent_event_collects
---

# eth.uniswap\_v3.event\_collects

Ethereum Uniswap-V3 collect events.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `address`          | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `tick_lower`       | INTEGER           |
| `tick_upper`       | INTEGER           |
| `amount0`          | CHARACTER VARYING |
| `amount1`          | CHARACTER VARYING |
| `owner`            | CHARACTER VARYING |
| `recipient`        | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
