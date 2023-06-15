---
description: >-
  SQL table schema for goerli.beacon.attestations and
  goerli.beacon.recent_attestations
---

# goerli.beacon.attestations

Goerli table stores data about attestations made by validators on the Beacon Chain.

| Column Name         | Data Type         |
| ------------------- | ----------------- |
| `block_slot`        | DOUBLE            |
| `block_root`        | CHARACTER VARYING |
| `block_timestamp`   | BIGINT            |
| `index`             | DOUBLE            |
| `aggregation_bits`  | CHARACTER VARYING |
| `attestation_slot`  | DOUBLE            |
| `beacon_block_root` | CHARACTER VARYING |
| `source_epoch`      | DOUBLE            |
| `source_root`       | CHARACTER VARYING |
| `target_epoch`      | DOUBLE            |
| `target_root`       | CHARACTER VARYING |
| `signature`         | CHARACTER VARYING |
