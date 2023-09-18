---
description: SQL table schema for prices.trades_detailed
---

# Trade data

All trades from centralised exchanges (e.g. Coinbase), and SpiceAI computed trades. Includes addititonal columns, and or prices computed using swap routing algorithms, includes details about the computation (see `swap_route` column). Trades from DEXs can be found in the Ethereum namespace, e.g. for [Uniswap V3](https://docs.spice.xyz/reference/sql-query-tables/ethereum/uniswap-v3-tables).

| Column Name        | Data Type          | Description                                                         |
| ------------------ | ------------------ | ------------------------------------------------------------------- |
| pair               | CHARACTER VARYING  | Asset trading pair                                                  |
| price              | FLOAT              | Price of the asset at the given timestamp                           |
| timestamp_ms       | BIGINT             | Timestamp in milliseconds                                           |
| asset_id0          | CHARACTER VARYING  | Asset ID of the first asset in the trading pair                     |
| asset_id1          | CHARACTER VARYING  | Asset ID of the second asset in the trading pair                    |
| exchange           | CHARACTER VARYING  | Name of the exchange where the trade was executed                   |
| swap_route         | CHARACTER VARYING  | Route taken for the swap operation                                  |
