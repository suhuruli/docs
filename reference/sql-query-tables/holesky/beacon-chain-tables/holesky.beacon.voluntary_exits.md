---
description: >-
  SQL table schema for holesky.beacon.voluntary_exits and
  holesky.beacon.recent_voluntary_exits
---

# holesky.beacon.voluntary\_exits

Holesky  table stores data about voluntary exits of validators from the Beacon Chain.

| Column Name       | Data Type         | Description                                                |
| ----------------- | ----------------- | ---------------------------------------------------------- |
| `block_slot`      | DOUBLE            | Index of slot in the block the voluntary exit was made on. |
| `block_root`      | CHARACTER VARYING | Root hash of block the voluntary exit was made on.         |
| `block_timestamp` | BIGINT            | Timestamp of the block the voluntary exit was made on.     |
| `index`           | DOUBLE            | The index of the voluntary exit in the block.              |
| `epoch`           | DOUBLE            | The epoch when the voluntary exit was processed            |
| `validator_index` | DOUBLE            | The index of the validator who made the validator index    |
| `signature`       | CHARACTER VARYING | Signature of the voluntary exit.                           |
