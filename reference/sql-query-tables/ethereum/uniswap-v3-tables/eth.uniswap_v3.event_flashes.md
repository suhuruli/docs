---
description: >-
  SQL table schema for eth.uniswap_v3.event_flashes and
  eth.uniswap_v3.recent_event_flashes
---

# eth.uniswap\_v3.event\_flashes

Ethereum Uniswap-V3 flash events.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `address`          | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `amount0`          | CHARACTER VARYING |
| `amount1`          | CHARACTER VARYING |
| `paid0`            | CHARACTER VARYING |
| `paid1`            | CHARACTER VARYING |
| `sender`           | CHARACTER VARYING |
| `recipient`        | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
