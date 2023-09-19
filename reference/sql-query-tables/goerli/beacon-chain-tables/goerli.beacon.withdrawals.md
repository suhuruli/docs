---
description: >-
  SQL table schema for goerli.beacon.withdrawals and
  goerli.beacon.recent_withdrawals
---

# goerli.beacon.withdrawals

Withdrawals of ETH from the beacon chain to the Goerli testnet chain.

| Column Name        | Data Type         | Description                                              |
| ------------------ | ----------------- | -------------------------------------------------------- |
| `block_slot`       | DOUBLE            | Index of slot in the block the slashing was processed.   |
| `block_root`       | CHARACTER VARYING | Root hash of block the slashing was processed.           |
| `block_timestamp`  | BIGINT            | Timestamp of the block the slashing was processed.       |
| `withdrawal_index` | DOUBLE            | The index of the withdrawal within the block.            |
| `validator_index`  | DOUBLE            | The index for the validator who made the change request. |
| `address`          | CHARACTER VARYING | The address that the ETH was withdrawn to.               |
| `amount`           | DOUBLE            | Amount of ETH withdrawn.                                 |
