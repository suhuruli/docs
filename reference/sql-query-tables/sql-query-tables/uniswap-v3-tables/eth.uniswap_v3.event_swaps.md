---
description: >-
  SQL table schema for eth.uniswap_v3.event_swaps and
  eth.uniswap_v3.recent_event_swaps
---

# eth.uniswap\_v3.event\_swaps

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `address`          | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `amount0`          | CHARACTER VARYING |
| `amount1`          | CHARACTER VARYING |
| `sqrt_price_x96`   | CHARACTER VARYING |
| `liquidity`        | CHARACTER VARYING |
| `tick`             | INTEGER           |
| `sender`           | CHARACTER VARYING |
| `recipient`        | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
