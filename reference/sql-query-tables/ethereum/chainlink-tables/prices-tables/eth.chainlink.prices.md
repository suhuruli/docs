---
description: SQL table schema for eth.chainlink.prices and eth.chainlink.recent_prices
---

# eth.chainlink.prices

Prices per price oracle data feeds on the ethereum network.

| Column Name        | Data Type         | Description                                                                            |
| ------------------ | ----------------- | -------------------------------------------------------------------------------------- |
| `oracle_address`   | CHARACTER VARYING | The address of the oracle which emitted the latest answer for the price of this asset. |
| `asset_address`    | CHARACTER VARYING | The address of the asset which the latest answer for the price refers to.              |
| `price_wei`        | CHARACTER VARYING | The latest answer for the price of the asset, in wei.                                  |
| `block_number`     | BIGINT            | The block number the answer was emitted on.                                            |
| `block_timestamp`  | BIGINT            | The block timestamp the answer was emitted on.                                         |
| `block_hash`       | CHARACTER VARYING | The block hash the answer was emitted on.                                              |
| `transaction_hash` | CHARACTER VARYING | The transaction hash the answer was emitted on.                                        |
