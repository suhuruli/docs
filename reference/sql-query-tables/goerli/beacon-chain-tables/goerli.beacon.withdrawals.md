---
description: >-
  SQL table schema for goerli.beacon.withdrawals and
  goerli.beacon.recent_withdrawals
---

# goerli.beacon.withdrawals

Withdrawals of ETH from the beacon chain to the Goerli testnet chain.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `block_slot`       | DOUBLE            |
| `block_root`       | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `withdrawal_index` | DOUBLE            |
| `validator_index`  | DOUBLE            |
| `address`          | CHARACTER VARYING |
| `amount`           | DOUBLE            |
