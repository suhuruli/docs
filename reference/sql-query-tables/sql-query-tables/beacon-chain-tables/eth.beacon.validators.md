---
description: SQL table schema for eth.validators
---

# eth.beacon.validators

| Column Name                    | Data Type         |
| ------------------------------ | ----------------- |
| `validator_index`              | DECIMAL           |
| `balance_gwei`                 | DECIMAL           |
| `status`                       | CHARACTER VARYING |
| `activation_eligibility_epoch` | DECIMAL           |
| `activation_epoch`             | DECIMAL           |
| `effective_balance`            | DECIMAL           |
| `exit_epoch`                   | DECIMAL           |
| `pubkey`                       | CHARACTER VARYING |
| `slashed`                      | BOOLEAN           |
| `withdrawable_epoch`           | DECIMAL           |
| `withdrawal_credentials`       | CHARACTER VARYING |
| `updated_at`                   | BIGINT            |
