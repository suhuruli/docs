---
description: SQL table schema for eth.aave_v2.loans and r eth.aave_v2.loan_updates
---

# eth.aave\_v2.loans

All Ethereum updates to aave v2 loans.

| Column Name            | Data Type         | Description                                                                       |
| ---------------------- | ----------------- | --------------------------------------------------------------------------------- |
| `lending_pool_address` | CHARACTER VARYING | The address of the contract that defines this lending pool.                       |
| `user_address`         | CHARACTER VARYING | The address of the user interacting with this pool.                               |
| `asset_address`        | CHARACTER VARYING | The address of the contract defining the asset being collateralized.              |
| `debt_wei`             | CHARACTER VARYING | The amount of loan debt, in wei.                                                  |
| `asset_decimals`       | INTEGER           | The number of decimals used in the fixed point representation of the asset value. |
| `block_number`         | BIGINT            | The number of the block in which this loan was issued.                            |
| `block_timestamp`      | BIGINT            | The timestamp of the block in which this loan was issued.                         |
| `block_hash`           | CHARACTER VARYING | The hash of the block in which this loan was issued.                              |
| `transaction_hash`     | CHARACTER VARYING | The hash of the transaction in which this loan was issued.                        |
