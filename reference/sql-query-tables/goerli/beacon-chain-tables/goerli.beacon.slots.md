---
description: SQL table schema for goerli.beacon.slots and goerli.beacon.recent_slots
---

# goerli.beacon.slots

Goerli Beacon Chain table contains data about each slot in the Beacon Chain.

| Column Name                               | Data Type         | Description                                                                                  |
| ----------------------------------------- | ----------------- | -------------------------------------------------------------------------------------------- |
| `block_slot`                              | DOUBLE            | Index of slot                                                                                |
| `block_epoch`                             | DOUBLE            | The epoch in which the slot belongs.                                                         |
| `block_timestamp`                         | BIGINT            | The timestamp of the block that was produced in the slot.                                    |
| `proposer_index`                          | DOUBLE            | The index of the validator that proposed the block that was produced in the slot.            |
| `skipped`                                 | BOOLEAN           | A boolean value indicating whether the slot was skipped.                                     |
| `block_root`                              | CHARACTER VARYING | The root hash of the block that was produced in the slot.                                    |
| `parent_root`                             | CHARACTER VARYING | The root hash of the parent block of the block that was produced in the slot.                |
| `state_root`                              | CHARACTER VARYING | The root hash of the state tree after the block that was produced in the slot was processed. |
| `randao_reveal`                           | CHARACTER VARYING | The RANDAO reveal of the validator that proposed the block that was produced in the slot.    |
| `graffiti`                                | CHARACTER VARYING | An optional field that can be used to add a message to the block                             |
| `eth1_block_hash`                         | CHARACTER VARYING | Hash of the ETH block containing the deposit contract                                        |
| `eth1_deposit_root`                       | CHARACTER VARYING | The root hash of the deposits made to the beacon chain in the slot.                          |
| `eth1_deposit_count`                      | DOUBLE            | The number of deposits that were made to the Beacon Chain in the slot.                       |
| `signature`                               | CHARACTER VARYING | Signature of produced block                                                                  |
| `attestations_count`                      | DOUBLE            | Number of attestations for the selected block                                                |
| `deposits_count`                          | DOUBLE            | Count of deposits include d in the proposed block                                            |
| `proposer_slashings_count`                | DOUBLE            | Count of proposer slashings in the proposed block                                            |
| `attester_slashings_count`                | DOUBLE            | Count of attester slashings in the proposed block                                            |
| `voluntary_exits_count`                   | DOUBLE            | Count of validators exiting the network                                                      |
| `sync_aggregate_sync_committee_bits`      | CHARACTER VARYING | Sync aggregate sync committee bits included in the proposed block.                           |
| `sync_aggregate_sync_committee_signature` | CHARACTER VARYING | Sync aggregate sync committee signature included in the proposed block.                      |
| `execution_payload_block_number`          | DOUBLE            | Block number in the execution layer where the execution payload was included.                |
| `execution_payload_block_hash`            | CHARACTER VARYING | Block hash in the execution layer where the execution payload was included.                  |
| `bls_to_execution_changes_count`          | DOUBLE            | Count of BLS to execution changes in the proposed block.                                     |
| `withdrawals_count`                       | DOUBLE            | Count of withdrawals included in the proposed block                                          |
