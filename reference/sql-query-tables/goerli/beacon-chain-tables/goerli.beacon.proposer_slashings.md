---
description: >-
  SQL table schema for goerli.beacon.proposer_slashings and
  goerli.beacon.recent_proposer_slashings
---

# goerli.beacon.proposer\_slashings

| Column Name               | Data Type         |
| ------------------------- | ----------------- |
| `block_slot`              | DOUBLE            |
| `block_root`              | CHARACTER VARYING |
| `block_timestamp`         | BIGINT            |
| `index`                   | DOUBLE            |
| `header_1_slot`           | DOUBLE            |
| `header_1_proposer_index` | DOUBLE            |
| `header_1_parent_root`    | CHARACTER VARYING |
| `header_1_state_root`     | CHARACTER VARYING |
| `header_1_body_root`      | CHARACTER VARYING |
| `header_1_signature`      | CHARACTER VARYING |
| `header_2_slot`           | DOUBLE            |
| `header_2_proposer_index` | DOUBLE            |
| `header_2_parent_root`    | CHARACTER VARYING |
| `header_2_state_root`     | CHARACTER VARYING |
| `header_2_body_root`      | CHARACTER VARYING |
| `header_2_signature`      | CHARACTER VARYING |
