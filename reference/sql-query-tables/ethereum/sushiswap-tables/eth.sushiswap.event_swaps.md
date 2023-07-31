---
description: >-
  SQL table schema for eth.sushiswap.event_swaps and
  eth.sushiswap.recent_event_swaps
---

# eth.sushiswap.event\_swaps

Ethereum Sushiswap swap events.

| Column Name        | Data Type         | Description                                                   |
| ------------------ | ----------------- | ------------------------------------------------------------- |
| `address`          | CHARACTER VARYING | The address of the contract that defines this pool.           |
| `log_index`        | BIGINT            | The index of this swap transaction in the block.              |
| `amount0_in`       | CHARACTER VARYING | The amount of the first token to be swapped by the sender.    |
| `amount1_in`       | CHARACTER VARYING | The amount of the second token to be swapped by the sender.   |
| `amount0_out`      | CHARACTER VARYING | The amount of the first token to be swapped by the receiver.  |
| `amount1_out`      | CHARACTER VARYING | The amount of the second token to be swapped by the receiver. |
| `sender`           | CHARACTER VARYING | The address of the initiator of this swap.                    |
| `to_address`       | CHARACTER VARYING | The address of the recipient of this swap.                    |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this swap occurred.      |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this swap occurred.       |
| `block_number`     | BIGINT            | The number of the block in which this swap occurred.          |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this swap occurred.            |
