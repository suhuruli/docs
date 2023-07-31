---
description: >-
  SQL table schema for eth.sushiswap.event_syncs and
  eth.sushiswap.recent_event_syncs
---

# eth.sushiswap.event\_syncs

Ethereum Sushiswap sync events.

| Column Name        | Data Type         | Description                                                                                                                       |
| ------------------ | ----------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `address`          | CHARACTER VARYING | The address of the contract that defines this pool.                                                                               |
| `log_index`        | BIGINT            | The index of this sync transaction in the block.                                                                                  |
| `reserve0`         | CHARACTER VARYING | <p>The amount of liquidity of the first token staked in this pool.</p><p></p><p>Provided as a convenience, but may overflow.</p>  |
| `reserve1`         | CHARACTER VARYING | <p>The amount of liquidity of the second token staked in this pool.</p><p></p><p>Provided as a convenience, but may overflow.</p> |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this sync occurred.                                                                          |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this sync occurred.                                                                           |
| `block_number`     | BIGINT            | The number of the block in which this sync occurred.                                                                              |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this sync occurred.                                                                                |
