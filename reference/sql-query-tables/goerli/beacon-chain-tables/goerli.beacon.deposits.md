---
description: SQL table schema for goerli.beacon.deposits and goerli.beacon.recent_deposits
---

# goerli.beacon.deposits

| Column Name              | Data Type         |
| ------------------------ | ----------------- |
| `block_slot`             | DOUBLE            |
| `block_root`             | CHARACTER VARYING |
| `block_timestamp`        | BIGINT            |
| `index`                  | DOUBLE            |
| `pubkey`                 | CHARACTER VARYING |
| `withdrawal_credentials` | CHARACTER VARYING |
| `amount`                 | DOUBLE            |
| `signature`              | CHARACTER VARYING |
