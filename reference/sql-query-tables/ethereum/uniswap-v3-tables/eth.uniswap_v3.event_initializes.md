---
description: >-
  SQL table schema for eth.uniswap_v3.event_initializes and
  eth.uniswap_v3.recent_event_initializes
---

# eth.uniswap\_v3.event\_initializes

Ethereum Uniswap-V3 initialize events.

| Column Name        | Data Type         | Description                                                                                                                                                                                       |
| ------------------ | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `address`          | CHARACTER VARYING | The address of the contract that defines this pool.                                                                                                                                               |
| `log_index`        | BIGINT            | The index of this collect event in the block.                                                                                                                                                     |
| `sqrt_price_x96`   | CHARACTER VARYING | The initial square root of the price of the pool, as a [Q64.96](https://docs.uniswap.org/contracts/v3/reference/core/libraries/FixedPoint96) fixed point number, encoded as a hexadecimal string. |
| `tick`             | INTEGER           | The initial tick of the pool.                                                                                                                                                                     |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this event occurred.                                                                                                                                         |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this event occurred.                                                                                                                                          |
| `block_number`     | BIGINT            | The number of the block in which this event occurred.                                                                                                                                             |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this event occurred.                                                                                                                                               |
