---
description: SQL table schema for goerli.beacon.deposits and goerli.beacon.recent_deposits
---

# goerli.beacon.deposits

Goerli table contains data about validator deposits made on the Beacon Chain.

| Column Name              | Data Type         | Description                                        |
| ------------------------ | ----------------- | -------------------------------------------------- |
| `block_slot`             | DOUBLE            | Index of slot in the block the deposit was made on |
| `block_root`             | CHARACTER VARYING | Root hash of block the deposit was made on.        |
| `block_timestamp`        | BIGINT            | Timestamp of the block the deposit was made on.    |
| `index`                  | DOUBLE            | The index of the deposit in the block.             |
| `pubkey`                 | CHARACTER VARYING | The public key of the validator who deposited.     |
| `withdrawal_credentials` | CHARACTER VARYING | Withdrawal credentials of the validator.           |
| `amount`                 | DOUBLE            | The amount of ETH deposited.                       |
| `signature`              | CHARACTER VARYING | Deposit signature.                                 |
