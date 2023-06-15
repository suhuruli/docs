---
description: SQL table schema for eth.sushiswap.pool_stats
---

# eth.sushiswap.pool\_stats

Ethereum Sushiswap tables Pool stats (reserves, etc) for each block.

| Column Name              | Data Type         |
| ------------------------ | ----------------- |
| `block_number`           | BIGINT            |
| `pool_address`           | CHARACTER VARYING |
| `reserve0`               | DOUBLE            |
| `reserve0_hex`           | CHARACTER VARYING |
| `reserve1`               | DOUBLE            |
| `reserve1_hex`           | CHARACTER VARYING |
| `block_timestamp_last`   | BIGINT            |
| `price0_cumulative_last` | CHARACTER VARYING |
| `price1_cumulative_last` | CHARACTER VARYING |
| `total_supply_hex`       | CHARACTER VARYING |
| `price0`                 | DOUBLE            |
| `price1`                 | DOUBLE            |
