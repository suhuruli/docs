---
description: SQL table schema for eth.uniswap_v3.pools
---

# eth.uniswap\_v3.pools

Ethereum Top 1000 Uniswap-V3 Pools.

| Column Name     | Data Type         | Description                                                                                    |
| --------------- | ----------------- | ---------------------------------------------------------------------------------------------- |
| `feeTier`       | BIGINT            | The [swap fee](https://docs.uniswap.org/concepts/protocol/fees#pool-fees-tiers) for this pool. |
| `id`            | CHARACTER VARYING | The id of this specific token:token liquidity pool.                                            |
| `token0_id`     | CHARACTER VARYING | The contract address that defines the first token in the pool.                                 |
| `token0_symbol` | CHARACTER VARYING | The human-readable symbol name for the first token in the pool, eg. "WETH".                    |
| `token1_id`     | CHARACTER VARYING | The contract address that defines the second token in the pool.                                |
| `token1_symbol` | CHARACTER VARYING | The human-readable symbol name for the second token in the pool, eg. "USDC".                   |
