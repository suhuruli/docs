---
description: SQL table schema for prices.ltc.gemini
---

# prices.ltc.gemini

HLOC values for LTC at 1 minute granularity from Gemini.

| Column Name | Data Type | Description                                                    |
| ----------- | --------- | -------------------------------------------------------------- |
| `timestamp` | TIMESTAMP | The timestamp of this pricing valuation.                       |
| `usd_high`  | DECIMAL   | The highest price, in USD, during the aggregated time period.  |
| `usd_low`   | DECIMAL   | The lowest price, in USD, during the aggregated time period.   |
| `usd_open`  | DECIMAL   | The initial/open price, in USD, of the aggregated time period. |
| `usd_close` | DECIMAL   | The final/close price, in USD, of the aggregated time period.  |
