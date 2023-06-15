---
description: SQL table schema for eth.aave_v2.loans and r eth.aave_v2.loan_updates
---

# eth.aave\_v2.loans

All Ethereum updates to aave v2 loans.

| Column Name            | Data Type         |
| ---------------------- | ----------------- |
| `lending_pool_address` | CHARACTER VARYING |
| `user_address`         | CHARACTER VARYING |
| `asset_address`        | CHARACTER VARYING |
| `debt_wei`             | CHARACTER VARYING |
| `asset_decimals`       | INTEGER           |
| `block_number`         | BIGINT            |
| `block_timestamp`      | BIGINT            |
| `block_hash`           | CHARACTER VARYING |
| `transaction_hash`     | CHARACTER VARYING |
