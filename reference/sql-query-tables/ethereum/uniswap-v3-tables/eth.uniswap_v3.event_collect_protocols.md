---
description: >-
  SQL table schema for eth.uniswap_v3.event_collect_protocols and
  eth.uniswap_v3.recent_event_collect_protocols
---

# eth.uniswap\_v3.event\_collect\_protocols

Ethereum Uniswap-V3 collect protocol events.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `address`          | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `amount0`          | CHARACTER VARYING |
| `amount1`          | CHARACTER VARYING |
| `sender`           | CHARACTER VARYING |
| `recipient`        | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
