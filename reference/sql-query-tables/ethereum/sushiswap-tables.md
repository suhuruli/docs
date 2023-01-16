# Sushiswap Tables

### Tables available to query

| Name                                | Description                                                  |
| ----------------------------------- | ------------------------------------------------------------ |
| `eth.sushiswap.pools`               | Top 1000 SushiSwap Pools                                     |
| `eth.sushiswap.pool_stats`          | Pool stats (reserves, etc) for each block                    |
| `eth.sushiswap.pool_stats_detailed` | Join between pools and pool\_stats                           |
| `eth.sushiswap.event_mints`         | SushiSwap mint events                                        |
| `eth.sushiswap.event_burns`         | SushiSwap burn events                                        |
| `eth.sushiswap.event_swaps`         | SushiSwap swap events                                        |
| `eth.sushiswap.event_syncs`         | SushiSwap sync events                                        |
| `eth.sushiswap.recent_event_mints`  | SushiSwap mint events from the last 30 minutes, \~128 blocks |
| `eth.sushiswap.recent_event_burns`  | SushiSwap burn events from the last 30 minutes, \~128 blocks |
| `eth.sushiswap.recent_event_swaps`  | SushiSwap swap events from the last 30 minutes, \~128 blocks |
| `eth.sushiswap.recent_event_syncs`  | SushiSwap sync events from the last 30 minutes, \~128 blocks |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
DESCRIBE eth.sushiswap.pools
DESCRIBE eth.sushiswap.pool_stats
DESCRIBE eth.sushiswap.pool_stats_detailed
```
