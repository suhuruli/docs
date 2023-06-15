---
description: SQL table schema for eth.beacon.deposits and eth.beacon.recent_deposits
---

# eth.beacon.deposits

Ethereum Beacon table contains data about validator deposits made on the Beacon Chain.

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
