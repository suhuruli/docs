# Sushiswap

### Tables available to query

| Name                                | Description                               |
| ----------------------------------- | ----------------------------------------- |
| `eth.sushiswap.pools`               | Top 100 Uniswap-V2 Pools                  |
| `eth.sushiswap.pool_stats`          | Pool stats (reserves, etc) for each block |
| `eth.sushiswap.pool_stats_detailed` | Join between pools and pool\_stats        |



```sql
DESCRIBE eth.sushiswap.pools
DESCRIBE eth.sushiswap.pool_stats
DESCRIBE eth.sushiswap.pool_stats_detailed
```
