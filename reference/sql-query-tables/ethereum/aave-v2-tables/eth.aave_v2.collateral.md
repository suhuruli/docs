---
description: SQL table schema for eth.aave_v2.collateral and eth.aave_v2.collateral_updates
---

# eth.aave\_v2.collateral

| Column Name                        | Data Type         |
| ---------------------------------- | ----------------- |
| `lending_pool_address`             | CHARACTER VARYING |
| `user_address`                     | CHARACTER VARYING |
| `asset_address`                    | CHARACTER VARYING |
| `amount_wei`                       | CHARACTER VARYING |
| `asset_decimals`                   | INTEGER           |
| `liquidation_threshold_percentage` | INTEGER           |
| `liquidation_bonus_percentage`     | INTEGER           |
| `block_number`                     | BIGINT            |
| `block_timestamp`                  | BIGINT            |
| `block_hash`                       | CHARACTER VARYING |
| `transaction_hash`                 | CHARACTER VARYING |
