# Cross-DEX

#### Compare daily average reserves and price across Uniswap-v2 and Sushiswap

**Typical query time**: <15 seconds

```sql
WITH sushiswap_pool AS (
    SELECT pool_address, token0_symbol, token1_symbol,
    AVG(reserve0) AS reserve0_avg,
    AVG(reserve1) AS reserve1_avg,
    AVG(price0) AS price0_avg,
    DATE_TRUNC('day', to_timestamp(block_timestamp_last)) AS "day"
    FROM eth.sushiswap.pool_stats_detailed
    WHERE token0_symbol = 'USDC' and token1_symbol = 'WETH'
    GROUP BY "day", pool_address, token0_symbol, token1_symbol
), uniswapv2_pool AS (
    SELECT pool_address, token0_symbol, token1_symbol,
    AVG(reserve0) AS reserve0_avg,
    AVG(reserve1) AS reserve1_avg,
    AVG(price0) AS price0_avg,
    DATE_TRUNC('day', to_timestamp(block_timestamp_last)) AS "day"
    FROM eth.uniswap_v2.pool_stats_detailed
    WHERE token0_symbol = 'USDC' and token1_symbol = 'WETH'
    GROUP BY "day", pool_address, token0_symbol, token1_symbol
)
select 'sushiswap' as "exchange", "day", token0_symbol, token1_symbol, reserve0_avg, reserve1_avg, price0_avg
from sushiswap_pool
UNION ALL
SELECT 'uniswap_v2' as "exchange", "day", token0_symbol, token1_symbol, reserve0_avg, reserve1_avg, price0_avg
from uniswapv2_pool
order by "day" desc
```
