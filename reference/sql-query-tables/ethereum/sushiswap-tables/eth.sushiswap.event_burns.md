---
description: >-
  SQL table schema for eth.sushiswap.event_burns and
  eth.sushiswap.recent_event_burns
---

# eth.sushiswap.event\_burns

Ethereum Sushiswap burn events.

| Column Name        | Data Type         | Description                                                          |
| ------------------ | ----------------- | -------------------------------------------------------------------- |
| `address`          | CHARACTER VARYING | The address of the contract that defines this pool.                  |
| `log_index`        | BIGINT            | The index of this burn transaction in the block.                     |
| `amount0`          | CHARACTER VARYING | The amount of the first token that is being burned out of the pool.  |
| `amount1`          | CHARACTER VARYING | The amount of the second token that is being burned out of the pool. |
| `sender`           | CHARACTER VARYING | The address of the burner.                                           |
| `to_address`       | CHARACTER VARYING | The address of the recipient of burned collateral.                   |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this burn occurred.             |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this burn occurred.              |
| `block_number`     | BIGINT            | The number of the block in which this burn occurred.                 |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this burn occurred.                   |

