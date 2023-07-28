---
description: >-
  SQL table schema for eth.uniswap_v3.event_collect_protocols and
  eth.uniswap_v3.recent_event_collect_protocols
---

# eth.uniswap\_v3.event\_collect\_protocols

Ethereum Uniswap-V3 collect protocol events.

| Column Name        | Data Type         | Description                                                    |
| ------------------ | ----------------- | -------------------------------------------------------------- |
| `address`          | CHARACTER VARYING | The address of the contract that defines this pool.            |
| `log_index`        | BIGINT            | The index of this collect event in the block.                  |
| `amount0`          | CHARACTER VARYING | The amount of the first token being collected.                 |
| `amount1`          | CHARACTER VARYING | The amount of the second token being collected.                |
| `sender`           | CHARACTER VARYING | The address initiating this collection.                        |
| `recipient`        | CHARACTER VARYING | The address of the recipient of this collection.               |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this collection occurred. |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this collection occurred.  |
| `block_number`     | BIGINT            | The number of the block in which this collection occurred.     |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this collection occurred.       |
