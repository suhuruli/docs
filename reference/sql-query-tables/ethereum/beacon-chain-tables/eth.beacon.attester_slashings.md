---
description: >-
  SQL table schema for eth.beacon.attester_slashings and
  eth.beacon.recent_attester_slashings
---

# eth.beacon.attester\_slashings

Ethereum Beacon table contains information about attester slashings on the Beacon Chain. Occurs when a validator has made conflicting attestations.

| Column Name                       | Data Type         | Description                                                                  |
| --------------------------------- | ----------------- | ---------------------------------------------------------------------------- |
| `block_slot`                      | DOUBLE            | Index of slot in the block the slashing was processed.                       |
| `block_root`                      | CHARACTER VARYING | Root hash of block the slashing was processed.                               |
| `block_timestamp`                 | BIGINT            | Timestamp of the block the slashing was processed.                           |
| `index`                           | DOUBLE            | The index of the slashing in the block.                                      |
| `attestation_1_attesting_indices` | CHARACTER VARYING | Validators attesting to the first conflicting attestation.                   |
| `attestation_1_slot`              | DOUBLE            | The slot with the first conflicting attestation.                             |
| `attestation_1_index`             | DOUBLE            | The index in the block of the first conflicting attestation.                 |
| `attestation_1_beacon_block_root` | CHARACTER VARYING | Root hash of the beacon block with the first conflicting attestation.        |
| `attestation_1_source_epoch`      | DOUBLE            | Epoch of the source block with the first conflicting attestation.            |
| `attestation_1_source_root`       | CHARACTER VARYING | The root hash of the source block with the first conflicting attestation.    |
| `attestation_1_target_epoch`      | DOUBLE            | Epoch of the target block with the first conflicting attestation.            |
| `attestation_1_target_root`       | CHARACTER VARYING | The root hash of the target block with the first conflicting attestation.    |
| `attestation_1_signature`         | CHARACTER VARYING | Signature of the first conflicting attestation.                              |
| `attestation_2_attesting_indices` | CHARACTER VARYING | Validators attesting to the second conflicting attestation.                  |
| `attestation_2_slot`              | DOUBLE            | The slot with the second conflicting attestation.                            |
| `attestation_2_index`             | DOUBLE            | The index in the block of the second conflicting attestation.                |
| `attestation_2_beacon_block_root` | CHARACTER VARYING | Root hash of the beacon block with the second conflicting attestation.       |
| `attestation_2_source_epoch`      | DOUBLE            | Epoch of the source block with the second conflicting attestation.           |
| `attestation_2_source_root`       | CHARACTER VARYING | The root hash of the source block with the second conflicting attestation.   |
| `attestation_2_target_epoch`      | DOUBLE            | Epoch of the target block with the second conflicting attestation.           |
| `attestation_2_target_root`       | CHARACTER VARYING | The root hash of the target block with the second conflicting attestation.   |
| `attestation_2_signature`         | CHARACTER VARYING | Signature of the second conflicting attestation.                             |
