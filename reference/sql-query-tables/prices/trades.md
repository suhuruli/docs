---
description: SQL table schema for spiceai.trades
---

# Trade data

All trades from centralised exchanges (e.g. Coinbase), and SpiceAI computed trades. For a more detailed view, see [`spiceai.trades_detailed`](trades\_detailed.md).

| Column Name        | Data Type          | Description                                                         |
| ------------------ | ------------------ | ------------------------------------------------------------------- |
| pair               | CHARACTER VARYING  | Asset trading pair                                                  |
| price              | FLOAT              | Price of the asset at the given timestamp                           |
| timestamp_ms       | BIGINT             | Timestamp in milliseconds                                           |
| asset_id0          | CHARACTER VARYING  | Asset ID of the first asset in the trading pair                     |
| asset_id1          | CHARACTER VARYING  | Asset ID of the second asset in the trading pair                    |


