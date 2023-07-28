---
description: SQL table schema for eth.uniswap_v2.pools
---

# eth.uniswap\_v2.pools

Ethereum top 1000 Uniswap-V2 Pools.

| Colum Name      | Data Type         | Description                                                                  |
| --------------- | ----------------- | ---------------------------------------------------------------------------- |
| `id`            | CHARACTER VARYING | The id of this specific token:token liquidity pool.                          |
| `token0_symbol` | CHARACTER VARYING | The human-readable symbol name for the first token in the pool, eg. "WETH".  |
| `token0_id`     | CHARACTER VARYING | The contract address that defines the first token in the pool.               |
| `token1_symbol` | CHARACTER VARYING | The human-readable symbol name for the second token in the pool, eg. "USDC". |
| `token1_id`     | CHARACTER VARYING | The contract address that defines the second token in the pool.              |
