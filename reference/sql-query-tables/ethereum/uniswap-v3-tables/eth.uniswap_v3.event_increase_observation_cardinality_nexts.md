---
description: >-
  SQL table schema for
  eth.uniswap_v3.event_increase_observation_cardinality_nexts and
  eth.uniswap_v3.recent_event_increase_observation_cardinality_nexts
---

# eth.uniswap\_v3.event\_increase\_observation\_cardinality\_nexts

Ethereum Uniswap-V3 increase observation cardinality next events.

| Column Name                        | Data Type         |
| ---------------------------------- | ----------------- |
| `address`                          | CHARACTER VARYING |
| `log_index`                        | BIGINT            |
| `observation_cardinality_next_old` | INTEGER           |
| `observation_cardinality_next_new` | INTEGER           |
| `transaction_hash`                 | CHARACTER VARYING |
| `block_timestamp`                  | BIGINT            |
| `block_number`                     | BIGINT            |
| `block_hash`                       | CHARACTER VARYING |
