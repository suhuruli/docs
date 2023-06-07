---
description: >-
  SQL table schema for eth.beacon.attestations and
  eth.beacon.recent_attestations
---

# eth.beacon.attestations

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
