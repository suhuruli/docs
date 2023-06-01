# Uniswap V3 Tables

### Tables available to query <a href="#tables-available-to-query" id="tables-available-to-query"></a>

| Name                                                                 | Description                                                                                    |
| -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `eth.uniswap_v3.pools`                                               | Top 1000 Uniswap-V3 Pools                                                                      |
| `eth.uniswap_v3.pool_stats`                                          | Pool stats (reserves, etc) for each block                                                      |
| `eth.uniswap_v3.event_burns`                                         | Uniswap-V3 burn events                                                                         |
| `eth.uniswap_v3.event_mints`                                         | Uniswap-V3 mint events                                                                         |
| `eth.uniswap_v3.event_swaps`                                         | Uniswap-V3 swap events                                                                         |
| `eth.uniswap_v3.event_set_fee_protocols`                             | Uniswap-V3 set fee protocol events                                                             |
| `eth.uniswap_v3.event_collects`                                      | Uniswap-V3 collect events                                                                      |
| `eth.uniswap_v3.event_collect_protocols`                             | Uniswap-V3 collect protocol events                                                             |
| `eth.uniswap_v3.event_flashes`                                       | Uniswap-V3 flash events                                                                        |
| `eth.uniswap_v3.event_increase_observation_cardinality_nexts`        | Uniswap-V3 increase observation cardinality next events                                        |
| `eth.uniswap_v3.event_initializes`                                   | Uniswap-V3 initialize events                                                                   |
| `eth.uniswap_v3.recent_event_burns`                                  | Uniswap-V3 burn events from the last 30 minutes, \~128 blocks                                  |
| `eth.uniswap_v3.recent_event_mints`                                  | Uniswap-V3 mint events from the last 30 minutes, \~128 blocks                                  |
| `eth.uniswap_v3.recent_event_swaps`                                  | Uniswap-V3 swap events from the last 30 minutes, \~128 blocks                                  |
| `eth.uniswap_v3.recent_event_set_fee_protocols`                      | Uniswap-V3 set fee protocol events from the last 30 minutes, \~128 blocks                      |
| `eth.uniswap_v3.recent_event_collects`                               | Uniswap-V3 collect events from the last 30 minutes, \~128 blocks                               |
| `eth.uniswap_v3.recent_event_collect_protocols`                      | Uniswap-V3 collect protocol events from the last 30 minutes, \~128 blocks                      |
| `eth.uniswap_v3.recent_event_flashes`                                | Uniswap-V3 flash events from the last 30 minutes, \~128 blocks                                 |
| `eth.uniswap_v3.recent_event_increase_observation_cardinality_nexts` | Uniswap-V3 increase observation cardinality next events from the last 30 minutes, \~128 blocks |
| `eth.uniswap_v3.recent_event_initializes`                            | Uniswap-V3 initialize events from the last 30 minutes, \~128 blocks                            |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
DESCRIBE eth.uniswap_v3.pools
DESCRIBE eth.uniswap_v3.pool_stats
DESCRIBE eth.uniswap_v3.event_mints
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

<table><thead><tr><th width="354.5">Table Name</th><th>Indexed Columns</th></tr></thead><tbody><tr><td><code>eth.uniswap_v3.pool_stats</code></td><td><code>block_number</code> <code>pool_address</code></td></tr><tr><td><code>eth.uniswap_v3.event_[mints/burns/swaps/etc]</code></td><td><code>block_number</code> <code>block_timestamp</code> <code>address</code></td></tr></tbody></table>
