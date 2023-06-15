---
description: >-
  SQL table schema for eth.beacon.voluntary_exits and
  eth.beacon.recent_voluntary_exits
---

# eth.beacon.voluntary\_exits

Ethereum Beacon table stores data about voluntary exits of validators from the Beacon Chain.

| Column Name       | Data Type         |
| ----------------- | ----------------- |
| `block_slot`      | DOUBLE            |
| `block_root`      | CHARACTER VARYING |
| `block_timestamp` | BIGINT            |
| `index`           | DOUBLE            |
| `epoch`           | DOUBLE            |
| `validator_index` | DOUBLE            |
| `signature`       | CHARACTER VARYING |
