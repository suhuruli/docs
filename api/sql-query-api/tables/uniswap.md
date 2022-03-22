# Uniswap

### Tables available to query

| Name                                 | Description                                              |
| ------------------------------------ | -------------------------------------------------------- |
| `eth.uniswap_v2.pools`               | Top 100 Uniswap-V2 Pools                                 |
| `eth.uniswap_v2.pool_stats`          | Pool stats (reserves, etc) for each block                |
| `eth.uniswap_v2.pool_stats_detailed` | Join between pools and pool\_stats                       |
| `eth.uniswap_v3.pools`               | Top 100 Uniswap-V3 Pools                                 |
| `eth.uniswap_v3.pool_stats`          | (Coming Soon!) Pool stats (reserves, etc) for each block |



```sql
DESCRIBE eth.uniswap_v2.pools
DESCRIBE eth.uniswap_v2.pool_stats
DESCRIBE eth.uniswap_v2.pool_stats_detailed
DESCRIBE eth.uniswap_v3.pools
```
