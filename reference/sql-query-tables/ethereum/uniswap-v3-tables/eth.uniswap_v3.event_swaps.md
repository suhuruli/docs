---
description: >-
  SQL table schema for eth.uniswap_v3.event_swaps and
  eth.uniswap_v3.recent_event_swaps
---

# eth.uniswap\_v3.event\_swaps

Ethereum Uniswap-V3 swap events.

| Column Name        | Data Type         | Description                                                                                                                                                                                               |
| ------------------ | ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `address`          | CHARACTER VARYING | The address of the contract that defines this pool.                                                                                                                                                       |
| `log_index`        | BIGINT            | The index of this burn transaction in the block.                                                                                                                                                          |
| `amount0`          | CHARACTER VARYING | The change in the amount of the first token staked in the pool as a result of this swap.                                                                                                                  |
| `amount1`          | CHARACTER VARYING | The change in the amount of the second token staked in the pool as a result of this swap.                                                                                                                 |
| `sqrt_price_x96`   | CHARACTER VARYING | The square root of the price of the pool after this swap, as a [Q64.96](https://docs.uniswap.org/contracts/v3/reference/core/libraries/FixedPoint96) fixed point number, encoded as a hexadecimal string. |
| `liquidity`        | CHARACTER VARYING | The amount of liquidity in the pool after this swap.                                                                                                                                                      |
| `tick`             | INTEGER           | The tick in which this swap occurred.                                                                                                                                                                     |
| `sender`           | CHARACTER VARYING | The address of the sender of this swap.                                                                                                                                                                   |
| `recipient`        | CHARACTER VARYING | The address of the recipient of this swap.                                                                                                                                                                |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this swap occurred.                                                                                                                                                  |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this swap occurred.                                                                                                                                                   |
| `block_number`     | BIGINT            | The number of the block in which this swap occurred.                                                                                                                                                      |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this swap occurred.                                                                                                                                                        |
