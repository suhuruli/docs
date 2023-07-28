---
description: >-
  SQL table schema for eth.uniswap_v3.event_set_fee_protocols and
  eth.uniswap_v3.recent_event_set_fee_protocols
---

# eth.uniswap\_v3.event\_set\_fee\_protocols

Ethereum Uniswap-V3 set fee protocol events.

| Column Name         | Data Type         | Description                                                 |
| ------------------- | ----------------- | ----------------------------------------------------------- |
| `address`           | CHARACTER VARYING | The address of the contract that defines this pool.         |
| `log_index`         | BIGINT            | The index of this burn transaction in the block.            |
| `fee_protocol0_old` | INTEGER           | The previous value of the fee protocol on the first token.  |
| `fee_protocol0_new` | INTEGER           | The new value of the fee protocol on the first token.       |
| `fee_protocol1_old` | INTEGER           | The previous value of the fee protocol on the second token. |
| `fee_protocol1_new` | INTEGER           | The new value of the fee protocol on the second token.      |
| `transaction_hash`  | CHARACTER VARYING | The hash of the transaction in which this event occurred.   |
| `block_timestamp`   | BIGINT            | The timestamp of the block in which this event occurred.    |
| `block_number`      | BIGINT            | The number of the block in which this event occurred.       |
| `block_hash`        | CHARACTER VARYING | The hash of the block in which this event occurred.         |
