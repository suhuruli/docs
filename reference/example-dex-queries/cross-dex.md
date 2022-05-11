# Cross-DEX

#### Compare daily average reserves and price across Uniswap-v2 and Sushiswap

**Typical query time**: <15 seconds

```sql
WITH sushiswap_pool AS (
    select "day", pool_address, token0_symbol, token1_symbol,
    avg(reserve0) as reserve0_avg,
    avg(reserve1) as reserve1_avg,
    avg(price0) as price0_avg
    from (select pool_address, token0_symbol, token1_symbol, DATE_TRUNC('day', to_timestamp(block_timestamp_last)) as "day", reserve0, reserve1, price0
        from eth.sushiswap.pool_stats_detailed WHERE token0_symbol = 'USDC' and token1_symbol = 'WETH')
    group by "day", pool_address, token0_symbol, token1_symbol
), uniswapv2_pool AS (
    select "day", pool_address, token0_symbol, token1_symbol,
    avg(reserve0) as reserve0_avg,
    avg(reserve1) as reserve1_avg,
    avg(price0) as price0_avg
    from (select pool_address, token0_symbol, token1_symbol, DATE_TRUNC('day', to_timestamp(block_timestamp_last)) as "day", reserve0, reserve1, price0
        from eth.uniswap_v2.pool_stats_detailed WHERE token0_symbol = 'USDC' and token1_symbol = 'WETH')
    group by "day", pool_address, token0_symbol, token1_symbol
)
select 'sushiswap' as "exchange", "day", token0_symbol, token1_symbol, reserve0_avg, reserve1_avg, price0_avg
from sushiswap_pool
UNION ALL
SELECT 'uniswap_v2' as "exchange", "day", token0_symbol, token1_symbol, reserve0_avg, reserve1_avg, price0_avg
from uniswapv2_pool
order by "day" desc
```
