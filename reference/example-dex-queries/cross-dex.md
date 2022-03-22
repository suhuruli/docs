# Cross-DEX



#### Compare reserves and price across Uniswap-v2 and Sushiswap

**Typical query time**: <15 seconds

```sql
WITH sushiswap_pool AS (
    SELECT *
    FROM eth.sushiswap.pool_stats_detailed
    WHERE token0_symbol = 'USDC' and token1_symbol = 'WETH'
    ORDER BY block_number DESC
    LIMIT 500
), uniswapv2_pool AS (
    SELECT *
    FROM eth.uniswap_v2.pool_stats_detailed
    WHERE token0_symbol = 'USDC' and token1_symbol = 'WETH'
    ORDER BY block_number DESC
    LIMIT 500
)
select 'sushiswap' as "exchange", token0_symbol, token1_symbol, avg(reserve0) as reserve0, avg(reserve1) as reserve1, avg(price0) as price0
from sushiswap_pool
group by pool_address, token0_symbol, token1_symbol
UNION ALL
SELECT 'uniswap_v2' as "exchange", token0_symbol, token1_symbol, avg(reserve0) as reserve0, avg(reserve1) as reserve1, avg(price0) as price0
from uniswapv2_pool
group by pool_address, token0_symbol, token1_symbol
```
