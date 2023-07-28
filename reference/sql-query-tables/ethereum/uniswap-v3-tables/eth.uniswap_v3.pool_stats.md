---
description: SQL table schema for eth.uniswap_v3.pool_stats
---

# eth.uniswap\_v3.pool\_stats

Ethereum Uniswap-V3 Pool stats (reserves, etc) for each block.

| Column Name                  | Data Type         | Description                                                                                                                          |
| ---------------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `block_number`               | BIGINT            | The number of the block at which these stats were calculated.                                                                        |
| `pool_address`               | CHARACTER VARYING | The address of the contract that defines this pool.                                                                                  |
| `liquidity_hex`              | CHARACTER VARYING | The total liquidity tokens for this pool, encoded as a hexadecimal string.                                                           |
| `max_liquidity_per_tick_hex` | CHARACTER VARYING | The maximum liquidity in the pool's "tick" timeframe, encoded as a hexadecimal string.                                               |
| `slot0_sqrt_price_x96_hex`   | CHARACTER VARYING | [The fixed width Uniswap v3 slot price embedding](https://blog.uniswap.org/uniswap-v3-math-primer), encoded as a hexadecimal string. |

