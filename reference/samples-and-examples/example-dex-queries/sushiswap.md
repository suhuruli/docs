# Sushiswap

### Pool Stats

**Typical query time**: <10 seconds

```sql
SELECT block_number,
    block_timestamp_last,
    reserve0,
    reserve1,
    price0,
    price1
FROM eth.sushiswap.pool_stats_detailed
WHERE token0_symbol = 'USDC' AND token1_symbol = 'WETH'
  and block_timestamp_last > UNIX_TIMESTAMP() - 60*60 -- 1 hour
ORDER BY block_number DESC
LIMIT 10
```

### Recent Changes in Price by Block Number

**Typical query time**: <10 seconds

```sql
SELECT min(block_number) as block_number,
    min(block_timestamp_last) as block_timestamp,
    reserve0 AS "USDC Pool Liquidity",
    reserve1 AS "WETH Pool Liquidity",
    price0 AS "WETH/USDC",
    price1 AS "USDC/WETH"
FROM eth.sushiswap.pool_stats_detailed
WHERE token0_symbol = 'USDC' AND token1_symbol = 'WETH'
  and block_timestamp_last > UNIX_TIMESTAMP() - 60*60 -- 1 hour
GROUP BY price0, price1, reserve0, reserve1
ORDER BY block_number DESC
LIMIT 10
```

### Advanced Liquidity Aggregations for USD Token Pairs

**Typical query time**: <10 seconds

```sql
SELECT token0_symbol, token1_symbol,
    min(block_number) AS min_block_number,
    max(block_number) AS max_block_number,
    max(reserve0) AS max_liquidity0,
    min(reserve0) AS min_liquidity0,
    avg(reserve0) AS avg_liquidity0,
    max(reserve1) AS max_liquidity1,
    min(reserve1) AS min_liquidity1,
    avg(reserve1) AS avg_liquidity1,
    max(price0) AS max_price0,
    min(price0) AS min_price0,
    avg(price0) AS avg_price0
FROM eth.uniswap_v2.pool_stats_detailed
WHERE (token0_symbol LIKE '%USD%' OR token1_symbol LIKE '%USD%')
  and block_timestamp_last > UNIX_TIMESTAMP() - 60*60 -- 1 hour
GROUP BY pool_address, token0_symbol, token1_symbol
ORDER BY avg_liquidity1 DESC
LIMIT 10
```

### Liquidity Data Aggregated by Hour

**Typical query time**: <10 seconds

```sql
SELECT "hour", 
       pool_address, 
       token0_symbol, 
       token1_symbol, 
       reserve0_avg, 
       reserve1_avg, 
       reserve0_max, 
       reserve1_max
FROM eth.sushiswap.pool_liquidity_stats_by_hour
ORDER BY "hour" DESC
LIMIT 10
```

#### Over the past few days, which pair that included USDC had the largest change in liquidity during a single hour?

**Typical query time**: <10 seconds

```sql
SELECT "hour", change_in_min_reserve0, change_in_min_reserve1, pool_address, token0_symbol, token1_symbol
FROM (
    SELECT "hour", reserve0_min_next_hour - reserve0_min as change_in_min_reserve0, reserve1_min_next_hour - reserve1_min as change_in_min_reserve1, pool_address, token0_symbol, token1_symbol
    FROM (
        SELECT
            "hour",
            reserve0_min,
            reserve1_min,
            pool_address,
            token0_symbol,
            token1_symbol,
            LEAD(reserve0_min,1) OVER (
                PARTITION BY pool_address
                ORDER BY "hour"
            ) reserve0_min_next_hour,
            LEAD(reserve1_min,1) OVER (
                PARTITION BY pool_address
                ORDER BY "hour"
            ) reserve1_min_next_hour
        FROM 
            eth.sushiswap.pool_liquidity_stats_by_hour
        WHERE "hour" > '2022-02-10 00:00:00.000'
    )
)
WHERE change_in_min_reserve0 IS NOT NULL AND change_in_min_reserve1 IS NOT NULL AND (token0_symbol = 'USDC' OR token1_symbol = 'USDC')
ORDER BY change_in_min_reserve0 desc
LIMIT 10
```

### Sushiswap top 10 pools with highest number of swaps

**Typical query time**: <10 seconds

```sql
SELECT address,
       count(1) AS tx_count
FROM eth.sushiswap.recent_event_swaps
GROUP BY address
ORDER BY tx_count DESC
LIMIT 10
```
