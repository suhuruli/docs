---
description: Example queries that use the SpiceAI token trade datasets
---

## Trades

### Get all trades of a given token pair today
Get per-minute price data for a trading pair, e.g. BTC-ETH, using the end of minute price (`close`, other options available), in the last two hours.

```sql
SELECT "close" as price
FROM spiceai.prices
WHERE pair='BTC-ETH'
AND "timestamp" > TIMESTAMPADD(HOUR, -2, CURRENT_TIMESTAMP())
```

## Get the number of trades per day for a given pair over the trailing 30 days
Get the amount of trade volume for a given pair, per day over the trailing last 30 days.

**Typical query time**: 2 seconds

```sql
SELECT TO_DATE(trades.timestamp_ms/1000) AS trade_date, count(pair) AS trade_count
FROM spiceai.trades
WHERE pair='XRP-USDT'
AND trades.timestamp_ms > 1000*(UNIX_TIMESTAMP() - 86400*30)
GROUP BY trade_date
ORDER BY trade_date DESC;
```

## Get the most frequently traded pairs on Coinbase today.
Get the most traded pairs from Coinbase today. Note, requires `spiceai.trades_detailed` not `spiceai.trades`.

**Typical query time**: ~1.5 seconds

```sql
SELECT pair, count(pair)
FROM spiceai.trades_detailed
WHERE exchange='coinbase'
AND trades.timestamp_ms > 1000*(UNIX_TIMESTAMP()  - 86400)
GROUP BY pair
ORDER BY count(pair) DESC
```

