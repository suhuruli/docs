---
description: >-
  SQL table schema for eth.sushiswap.event_mints and
  eth.sushiswap.recent_event_mints
---

# eth.sushiswap.event\_mints

Ethereum Sushiswap mint events.

| Column Name        | Data Type         | Description                                                        |
| ------------------ | ----------------- | ------------------------------------------------------------------ |
| `address`          | CHARACTER VARYING | The address of the contract that defines this pool.                |
| `log_index`        | BIGINT            | The index of this mint transaction in the block.                   |
| `amount0`          | CHARACTER VARYING | The amount of the first token that is being minted into the pool.  |
| `amount1`          | CHARACTER VARYING | The amount of the second token that is being minted into the pool. |
| `sender`           | CHARACTER VARYING | The address of the minter.                                         |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this mint occurred.           |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this mint occurred.            |
| `block_number`     | BIGINT            | The number of the block in which this mint occurred.               |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this mint occurred.                 |
