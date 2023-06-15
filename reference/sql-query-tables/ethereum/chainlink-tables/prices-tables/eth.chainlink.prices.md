---
description: SQL table schema for eth.chainlink.prices and eth.chainlink.recent_prices
---

# eth.chainlink.prices

Prices per price oracle data feeds on the ethereum network.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `oracle_address`   | CHARACTER VARYING |
| `asset_address`    | CHARACTER VARYING |
| `price_wei`        | CHARACTER VARYING |
| `block_number`     | BIGINT            |
| `block_timestamp`  | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
