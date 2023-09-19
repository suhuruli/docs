---
description: SQL table schema for eth.validators
---

# eth.beacon.validators

Ethereum Beacon latest validators, with their status and current balance.

| Column Name                    | Data Type         | Description                                               |
| ------------------------------ | ----------------- | --------------------------------------------------------- |
| `validator_index`              | DECIMAL           | The unique identifier for each validator                  |
| `balance_gwei`                 | DECIMAL           | The balance of ETH in gwei for each validator.            |
| `status`                       | CHARACTER VARYING | Validator status, either `active` or `exited`.            |
| `activation_eligibility_epoch` | DECIMAL           | Epoch from when validator can activate.                   |
| `activation_epoch`             | DECIMAL           | Epoch when validator did activate.                        |
| `effective_balance`            | DECIMAL           | Validator's effective ETH balance, inclusive of slashing. |
| `exit_epoch`                   | DECIMAL           | Epoch when the validator will exit.                       |
| `pubkey`                       | CHARACTER VARYING | Validator's public key                                    |
| `slashed`                      | BOOLEAN           | True if the validator has been slashed, False otherwise.  |
| `withdrawable_epoch`           | DECIMAL           | Epoch from when validator can withdraw                    |
| `withdrawal_credentials`       | CHARACTER VARYING | Withdrawal credential data for the validator.             |
| `updated_at`                   | BIGINT            | Last time validator details were updated                  |
