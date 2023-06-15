---
description: SQL table schema for eth.sushiswap.pool_stats_detailed
---

# eth.sushiswap.pool\_stats\_detailed

Ethereum Sushiswap Join between pools and pool\_stats.

| Column Name            | Data Type         |
| ---------------------- | ----------------- |
| `block_number`         | BIGINT            |
| `pool_address`         | CHARACTER VARYING |
| `token0_symbol`        | CHARACTER VARYING |
| `token1_symbol`        | CHARACTER VARYING |
| `reserve0`             | DOUBLE            |
| `reserve1`             | DOUBLE            |
| `price0`               | DOUBLE            |
| `price1`               | DOUBLE            |
| `total_supply_hex`     | CHARACTER VARYING |
| `token0_id`            | CHARACTER VARYING |
| `token1_id`            | CHARACTER VARYING |
| `block_timestamp_last` | BIGINT            |
