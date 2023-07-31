---
description: >-
  SQL table schema for goerli.beacon.proposer_slashings and
  goerli.beacon.recent_proposer_slashings
---

# goerli.beacon.proposer\_slashings

Goerli Beacon Chain table stores data about proposer slashings on the Beacon Chain. Proposer slashings occur when a validator has been found to have proposed two conflicting blocks for the same slot.

| Column Name               | Data Type         | Description                                                       |
| ------------------------- | ----------------- | ----------------------------------------------------------------- |
| `block_slot`              | DOUBLE            | Index of slot in the block the slashing was processed.            |
| `block_root`              | CHARACTER VARYING | Root hash of block the slashing was processed.                    |
| `block_timestamp`         | BIGINT            | Timestamp of the block the slashing was processed.                |
| `index`                   | DOUBLE            | The index of the slashing in the block.                           |
| `header_1_slot`           | DOUBLE            | Slot in the beacon chain the first conflicting block is for       |
| `header_1_proposer_index` | DOUBLE            | The validator's index whom proposed the first conflicting block.  |
| `header_1_parent_root`    | CHARACTER VARYING | The root hash of the first conflicting block's parent.            |
| `header_1_state_root`     | CHARACTER VARYING | The root hash of the first conflicting block's state trie.        |
| `header_1_body_root`      | CHARACTER VARYING | The root hash of the first conflicting block's body.              |
| `header_1_signature`      | CHARACTER VARYING | Signature of the first conflicting block.                         |
| `header_2_slot`           | DOUBLE            | Slot in the beacon chain the second conflicting block is for      |
| `header_2_proposer_index` | DOUBLE            | The validator's index whom proposed the second conflicting block. |
| `header_2_parent_root`    | CHARACTER VARYING | The root hash of the second conflicting block's parent.           |
| `header_2_state_root`     | CHARACTER VARYING | The root hash of the second conflicting block's state trie.       |
| `header_2_body_root`      | CHARACTER VARYING | The root hash of the second conflicting block's body.             |
| `header_2_signature`      | CHARACTER VARYING | Signature of the second conflicting block.                        |
