---
description: >-
  SQL table schema for eth.beacon.attester_slashings and
  eth.beacon.recent_attester_slashings
---

# eth.beacon.attester\_slashings

Ethereum Beacon table contains information about attester slashings on the Beacon Chain. Occurs when a validator has made conflicting attestations.

| Column Name                       | Data Type         |
| --------------------------------- | ----------------- |
| `block_slot`                      | DOUBLE            |
| `block_root`                      | CHARACTER VARYING |
| `block_timestamp`                 | BIGINT            |
| `index`                           | DOUBLE            |
| `attestation_1_attesting_indices` | CHARACTER VARYING |
| `attestation_1_slot`              | DOUBLE            |
| `attestation_1_index`             | DOUBLE            |
| `attestation_1_beacon_block_root` | CHARACTER VARYING |
| `attestation_1_source_epoch`      | DOUBLE            |
| `attestation_1_source_root`       | CHARACTER VARYING |
| `attestation_1_target_epoch`      | DOUBLE            |
| `attestation_1_target_root`       | CHARACTER VARYING |
| `attestation_1_signature`         | CHARACTER VARYING |
| `attestation_2_attesting_indices` | CHARACTER VARYING |
| `attestation_2_slot`              | DOUBLE            |
| `attestation_2_index`             | DOUBLE            |
| `attestation_2_beacon_block_root` | CHARACTER VARYING |
| `attestation_2_source_epoch`      | DOUBLE            |
| `attestation_2_source_root`       | CHARACTER VARYING |
| `attestation_2_target_epoch`      | DOUBLE            |
| `attestation_2_target_root`       | CHARACTER VARYING |
| `attestation_2_signature`         | CHARACTER VARYING |
