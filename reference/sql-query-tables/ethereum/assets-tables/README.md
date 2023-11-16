# Assets Tables

#### Tables available to query

| Name                                             | Description                                                    |
| ------------------------------------------------ | -------------------------------------------------------------- |
| [`eth.asset_transfers`](eth.asset\_transfers.md) | Asset Transfers represent exchanges of value between accounts. |

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns. The asset transfer table has indexes on `from_address`, `to_address` and `block_number.`
