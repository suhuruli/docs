---
description: SQL table schema for prices.eth.coinbase
---

# prices.eth.coinbase

HLOC values for ETH at 1 minute granularity from Coinbase.

| Column Name | Data Type | Description                                                    |
| ----------- | --------- | -------------------------------------------------------------- |
| `timestamp` | TIMESTAMP | The timestamp of this pricing valuation.                       |
| `usd_high`  | DECIMAL   | The highest price, in USD, during the aggregated time period.  |
| `usd_low`   | DECIMAL   | The lowest price, in USD, during the aggregated time period.   |
| `usd_open`  | DECIMAL   | The initial/open price, in USD, of the aggregated time period. |
| `usd_close` | DECIMAL   | The final/close price, in USD, of the aggregated time period.  |

