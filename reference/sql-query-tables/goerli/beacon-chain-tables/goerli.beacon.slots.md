---
description: SQL table schema for goerli.beacon.slots and goerli.beacon.recent_slots
---

# goerli.beacon.slots

Goerli Beacon Chain table contains data about each slot in the Beacon Chain.

| Column Name                               | Data Type         |
| ----------------------------------------- | ----------------- |
| `block_slot`                              | DOUBLE            |
| `block_epoch`                             | DOUBLE            |
| `block_timestamp`                         | BIGINT            |
| `proposer_index`                          | DOUBLE            |
| `skipped`                                 | BOOLEAN           |
| `block_root`                              | CHARACTER VARYING |
| `parent_root`                             | CHARACTER VARYING |
| `state_root`                              | CHARACTER VARYING |
| `randao_reveal`                           | CHARACTER VARYING |
| `graffiti`                                | CHARACTER VARYING |
| `eth1_block_hash`                         | CHARACTER VARYING |
| `eth1_deposit_root`                       | CHARACTER VARYING |
| `eth1_deposit_count`                      | DOUBLE            |
| `signature`                               | CHARACTER VARYING |
| `attestations_count`                      | DOUBLE            |
| `deposits_count`                          | DOUBLE            |
| `proposer_slashings_count`                | DOUBLE            |
| `attester_slashings_count`                | DOUBLE            |
| `voluntary_exits_count`                   | DOUBLE            |
| `sync_aggregate_sync_committee_bits`      | CHARACTER VARYING |
| `sync_aggregate_sync_committee_signature` | CHARACTER VARYING |
| `execution_payload_block_number`          | DOUBLE            |
| `execution_payload_block_hash`            | CHARACTER VARYING |
| `bls_to_execution_changes_count`          | DOUBLE            |
| `withdrawals_count`                       | DOUBLE            |
