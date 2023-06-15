---
description: SQL table schema for eth.validators
---

# eth.beacon.validators

Ethereum Beacon latest validators, with their status and current balance.

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
