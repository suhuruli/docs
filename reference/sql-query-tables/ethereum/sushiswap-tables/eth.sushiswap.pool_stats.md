---
description: SQL table schema for eth.sushiswap.pool_stats
---

# eth.sushiswap.pool\_stats

Ethereum Sushiswap tables Pool stats (reserves, etc) for each block.

| Column Name              | Data Type         | Description                                                                                                                       |
| ------------------------ | ----------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `block_number`           | BIGINT            | The number of the block at which these stats were calculated.                                                                     |
| `pool_address`           | CHARACTER VARYING | The address of the contract that defines this pool.                                                                               |
| `reserve0`               | DOUBLE            | <p>The amount of liquidity of the first token staked in this pool.</p><p></p><p>Provided as a convenience, but may overflow.</p>  |
| `reserve0_hex`           | CHARACTER VARYING | Lossless encoding of the full `reserve0` value as a hexadecimal string.                                                           |
| `reserve1`               | DOUBLE            | <p>The amount of liquidity of the second token staked in this pool.</p><p></p><p>Provided as a convenience, but may overflow.</p> |
| `reserve1_hex`           | CHARACTER VARYING | Lossless encoding of the full `reserve1` value as a hexadecimal string.                                                           |
| `block_timestamp_last`   | BIGINT            | The timestamp of the last block that updated this pool.                                                                           |
| `price0_cumulative_last` | CHARACTER VARYING | The last cumulative price of the first token, as reported by the contract.                                                        |
| `price1_cumulative_last` | CHARACTER VARYING | The last cumulative price of the second token, as reported by the contract.                                                       |
| `total_supply_hex`       | CHARACTER VARYING | The total supply of liquidity tokens for this pool, encoded as a hexadecimal string.                                              |
| `price0`                 | DOUBLE            | The price of the first token in this pool: `reserve0 / reserve1`.                                                                 |
| `price1`                 | DOUBLE            | The price of the second token in this pool: `reserve1 / reserve0`.                                                                |
