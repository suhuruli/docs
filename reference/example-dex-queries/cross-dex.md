# Cross-DEX

#### Compare minute-by-minute reserves and price across Uniswap-v2 and Sushiswap from the past month

**Typical query time**: <15 seconds

```sql
WITH sushiswap_liquidity AS (
    SELECT
    AVG(reserve0) AS usdc_reserve,
    AVG(reserve1) AS weth_reserve,
    AVG(price0) AS usdc_weth_price,
    DATE_TRUNC('minute', to_timestamp(block_timestamp_last)) AS "minute"
    FROM eth.sushiswap.pool_stats_detailed
    WHERE token0_symbol = 'USDC' and token1_symbol = 'WETH' 
      and block_timestamp_last > UNIX_TIMESTAMP() - 30*24*60*60 -- 30 days
    GROUP BY "minute", pool_address, token0_symbol, token1_symbol
    ORDER BY "minute" DESC
), uniswap_liquidity AS (
    SELECT
    AVG(reserve0) AS usdc_reserve,
    AVG(reserve1) AS weth_reserve,
    AVG(price0) AS usdc_weth_price,
    DATE_TRUNC('minute', to_timestamp(block_timestamp_last)) AS "minute"
    FROM eth.uniswap_v2.pool_stats_detailed
    WHERE token0_symbol = 'USDC' and token1_symbol = 'WETH'
      and block_timestamp_last > UNIX_TIMESTAMP() - 30*24*60*60 -- 30 days
    GROUP BY "minute", pool_address, token0_symbol, token1_symbol
    ORDER BY "minute" DESC
)

select 'sushiswap' as "exchange", "minute", usdc_reserve, weth_reserve, usdc_weth_price
from sushiswap_liquidity
UNION ALL
SELECT 'uniswap_v2' as "exchange", "minute", usdc_reserve, weth_reserve, usdc_weth_price
from uniswap_liquidity
order by "minute" desc
```

Run this query yourself using a [Kaggle notebook](https://www.kaggle.com/code/phillipleblanc/spice-xyz-dex-liquidity)
