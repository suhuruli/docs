---
description: SQL table schema for eth.uniswap_v3.pool_stats
---

# eth.uniswap\_v3.pool\_stats

Ethereum Uniswap-V3 Pool stats (reserves, etc) for each block.

| Column Name                  | Data Type         |
| ---------------------------- | ----------------- |
| `block_number`               | BIGINT            |
| `pool_address`               | CHARACTER VARYING |
| `liquidity_hex`              | CHARACTER VARYING |
| `max_liquidity_per_tick_hex` | CHARACTER VARYING |
| `slot0_sqrt_price_x96_hex`   | CHARACTER VARYING |
