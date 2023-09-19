---
description: SQL table schema for eth.uniswap_v2.pool_stats_detailed
---

# eth.uniswap\_v2.pool\_stats\_detailed

Ethereum Uniswap-V2 join between pools and pool\_stats.

| Column Name            | Data Type         | Description                                                                                                                       |
| ---------------------- | ----------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `block_number`         | BIGINT            | The number of the block at which these stats were calculated.                                                                     |
| `pool_address`         | CHARACTER VARYING | The address of the contract that defines this pool.                                                                               |
| `token0_symbol`        | CHARACTER VARYING | The human-readable symbol name for the first token in the pool, eg. "WETH".                                                       |
| `token1_symbol`        | CHARACTER VARYING | The contract address that defines the second token in the pool.                                                                   |
| `reserve0`             | DOUBLE            | <p>The amount of liquidity of the first token staked in this pool.</p><p></p><p>Provided as a convenience, but may overflow.</p>  |
| `reserve1`             | DOUBLE            | <p>The amount of liquidity of the second token staked in this pool.</p><p></p><p>Provided as a convenience, but may overflow.</p> |
| `price0`               | DOUBLE            | The price of the first token in this pool: `reserve0 / reserve1`.                                                                 |
| `price1`               | DOUBLE            | The price of the second token in this pool: `reserve1 / reserve0`.                                                                |
| `total_supply_hex`     | CHARACTER VARYING | The total supply of liquidity tokens for this pool, encoded as a hexadecimal string.                                              |
| `token0_id`            | CHARACTER VARYING | The contract address that defines the first token in the pool.                                                                    |
| `token1_id`            | CHARACTER VARYING | The contract address that defines the second token in the pool.                                                                   |
| `block_timestamp_last` | BIGINT            | The timestamp of the last block that updated this pool.                                                                           |
