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

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

<table><thead><tr><th width="354.5">Table Name</th><th>Indexed Columns</th></tr></thead><tbody><tr><td><code>eth.sushiswap.pool_stats</code></td><td><code>block_number</code> <code>pool_address</code></td></tr><tr><td><code>eth.sushiswap.pool_stats_detailed</code></td><td><code>block_number</code> <code>pool_address</code></td></tr><tr><td><code>eth.sushiswap.event_[mints/burns/swaps/syncs]</code></td><td><code>block_number</code> <code>block_timestamp</code> <code>address</code></td></tr></tbody></table>
