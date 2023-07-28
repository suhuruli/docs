---
description: >-
  SQL table schema for
  eth.uniswap_v3.event_increase_observation_cardinality_nexts and
  eth.uniswap_v3.recent_event_increase_observation_cardinality_nexts
---

# eth.uniswap\_v3.event\_increase\_observation\_cardinality\_nexts

Ethereum Uniswap-V3 increase observation cardinality next events.

| Column Name                        | Data Type         | Description                                               |
| ---------------------------------- | ----------------- | --------------------------------------------------------- |
| `address`                          | CHARACTER VARYING | The address of the contract that defines this pool.       |
| `log_index`                        | BIGINT            | The index of this event in the block.                     |
| `observation_cardinality_next_old` | INTEGER           |                                                           |
| `observation_cardinality_next_new` | INTEGER           |                                                           |
| `transaction_hash`                 | CHARACTER VARYING | The hash of the transaction in which this event occurred. |
| `block_timestamp`                  | BIGINT            | The timestamp of the block in which this event occurred.  |
| `block_number`                     | BIGINT            | The number of the block in which this event occurred.     |
| `block_hash`                       | CHARACTER VARYING | The hash of the block in which this event occurred.       |
