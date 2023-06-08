---
description: >-
  SQL table schema for eth.uniswap_v3.event_set_fee_protocols and
  eth.uniswap_v3.recent_event_set_fee_protocols
---

# eth.uniswap\_v3.event\_set\_fee\_protocols

| Column Name         | Data Type         |
| ------------------- | ----------------- |
| `address`           | CHARACTER VARYING |
| `log_index`         | BIGINT            |
| `fee_protocol0_old` | INTEGER           |
| `fee_protocol0_new` | INTEGER           |
| `fee_protocol1_old` | INTEGER           |
| `fee_protocol1_new` | INTEGER           |
| `transaction_hash`  | CHARACTER VARYING |
| `block_timestamp`   | BIGINT            |
| `block_number`      | BIGINT            |
| `block_hash`        | CHARACTER VARYING |
