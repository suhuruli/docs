---
description: SQL table schema for eth.sushiswap.pools
---

# eth.sushiswap.pools

Ethereum Top 1000 SushiSwap Pools.

| Column Name     | Data Type         | Description                                                                  |
| --------------- | ----------------- | ---------------------------------------------------------------------------- |
| `id`            | CHARACTER VARYING | The id of this specific token:token liquidity pool.                          |
| `token0_symbol` | CHARACTER VARYING | The human-readable symbol name for the first token in the pool, eg. "WETH".  |
| `token0_id`     | CHARACTER VARYING | The contract address that defines the first token in the pool.               |
| `token1_symbol` | CHARACTER VARYING | The human-readable symbol name for the second token in the pool, eg. "USDC". |
| `token1_id`     | CHARACTER VARYING | The contract address that defines the second token in the pool.              |
