---
description: SQL table schema for prices.btc.uniswap_v2
---

# prices.btc.uniswap\_v2

HLOC values for BTC at 1 minute granularity from Uniswap.

| Column Name | Data Type |                                                                |
| ----------- | --------- | -------------------------------------------------------------- |
| `timestamp` | TIMESTAMP | The timestamp of this pricing valuation.                       |
| `usd_high`  | DECIMAL   | The highest price, in USD, during the aggregated time period.  |
| `usd_low`   | DECIMAL   | The lowest price, in USD, during the aggregated time period.   |
| `usd_open`  | DECIMAL   | The initial/open price, in USD, of the aggregated time period. |
| `usd_close` | DECIMAL   | The final/close price, in USD, of the aggregated time period.  |
