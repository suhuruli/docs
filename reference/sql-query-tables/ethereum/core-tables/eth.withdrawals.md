---
description: SQL table schema for eth.withdrawals and eth.recent_withdrawals
---

# eth.withdrawals

Ethereum Block withdrawals.

| Column Name        | Data Type         | Description                                                             |
| ------------------ | ----------------- | ----------------------------------------------------------------------- |
| `withdrawal_index` | DOUBLE            | Unique identifier of the withdrawal (within the withdrawal table).      |
| `validator_index`  | DOUBLE            | Unique identifier of the validator (within the validator table).        |
| `amount`           | DOUBLE            | The amount of ETH withdrawn.                                            |
| `address`          | CHARACTER VARYING | The address of the withdrawing account.                                 |
| `block_timestamp`  | BIGINT            | Unix time when the block including this withdrawal was mined/validated. |
| `block_hash`       | CHARACTER VARYING | The hash of the block including this withdrawal                         |
| `block_number`     | BIGINT            | The number of the block including this withdrawal                       |
