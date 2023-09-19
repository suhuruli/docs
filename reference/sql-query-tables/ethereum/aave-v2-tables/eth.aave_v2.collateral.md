---
description: SQL table schema for eth.aave_v2.collateral and eth.aave_v2.collateral_updates
---

# eth.aave\_v2.collateral

All Ethereum updates to aave v2 collateral.

| Column Name                        | Data Type         | Description                                                                                                                                        |
| ---------------------------------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `lending_pool_address`             | CHARACTER VARYING | The address of the contract that defines this lending pool.                                                                                        |
| `user_address`                     | CHARACTER VARYING | The address of the user interacting with this pool.                                                                                                |
| `asset_address`                    | CHARACTER VARYING | The address of the contract defining the asset being collateralized.                                                                               |
| `amount_wei`                       | CHARACTER VARYING | The amount of collateral, in wei.                                                                                                                  |
| `asset_decimals`                   | INTEGER           | The number of decimals used in the fixed point representation of the asset value.                                                                  |
| `liquidation_threshold_percentage` | INTEGER           | The percentage threshold at which point this collateral is over-leveraged and [can be liquidated](https://docs.aave.com/faq/liquidations).         |
| `liquidation_bonus_percentage`     | INTEGER           | The percentage bonus a [liquidator receives on this asset](https://docs.aave.com/faq/liquidations) for successfully liquidating an unhealthy loan. |
| `block_number`                     | BIGINT            | The number of the block in which this collateral was issued.                                                                                       |
| `block_timestamp`                  | BIGINT            | The timestamp of the block in which this collateral was issued.                                                                                    |
| `block_hash`                       | CHARACTER VARYING | The hash of the block in which this collateral was issued.                                                                                         |
| `transaction_hash`                 | CHARACTER VARYING | The hash of the transaction in which this collateral was issued.                                                                                   |
