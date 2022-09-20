# Sushiswap Tables

### Tables available to query

| Name                                | Description                               |
| ----------------------------------- | ----------------------------------------- |
| `eth.sushiswap.pools`               | Top 1000 SushiSwap Pools                  |
| `eth.sushiswap.pool_stats`          | Pool stats (reserves, etc) for each block |
| `eth.sushiswap.pool_stats_detailed` | Join between pools and pool\_stats        |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
DESCRIBE eth.sushiswap.pools
DESCRIBE eth.sushiswap.pool_stats
DESCRIBE eth.sushiswap.pool_stats_detailed
```
