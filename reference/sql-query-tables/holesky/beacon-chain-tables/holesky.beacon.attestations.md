---
description: >-
  SQL table schema for holesky.beacon.attestations and
  holesky.beacon.recent_attestations
---

# holesky.beacon.attestations

Holesky table stores data about attestations made by validators on the Beacon Chain.

| Column Name         | Data Type         | Description                                                                   |
| ------------------- | ----------------- | ----------------------------------------------------------------------------- |
| `block_slot`        | DOUBLE            | Index of slot in the block the attestation was made on                        |
| `block_root`        | CHARACTER VARYING | Root hash of block the attestation was made on.                               |
| `block_timestamp`   | BIGINT            | Timestamp of the block the attestation was made on.                           |
| `index`             | DOUBLE            | Identifier of the validator's committee.                                      |
| `aggregation_bits`  | CHARACTER VARYING | The attestation's aggregation bits                                            |
| `attestation_slot`  | DOUBLE            | The slot for which block being attested for, is being considered in.          |
| `beacon_block_root` | CHARACTER VARYING | The root hash of the beacon block being attested to.                          |
| `source_epoch`      | DOUBLE            | Epoch of the source block.                                                    |
| `source_root`       | CHARACTER VARYING | The root hash of the source block (most recent justified block) attested to.  |
| `target_epoch`      | DOUBLE            | Epoch of the target block.                                                    |
| `target_root`       | CHARACTER VARYING | The root hash of the target block (first block in current epoch) attested to. |
| `signature`         | CHARACTER VARYING | BLS signature of aggregate validator signatures.                              |
