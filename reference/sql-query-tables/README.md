---
description: Ethereum base type tables available to query via SQL
---

# SQL Query Tables

#### Ethereum base type tables available to query

| Table Name                   | Description                                                              |
| ---------------------------- | ------------------------------------------------------------------------ |
| `eth.blocks`                 | Block headers                                                            |
| `eth.recent_blocks`          | Block headers from the last 30 minutes, \~128 blocks                     |
| `eth.transactions`           | Block transactions                                                       |
| `eth.recent_transactions`    | Block transactions from the last 30 minutes, \~128 blocks                |
| `eth.logs`                   | Transaction event logs                                                   |
| `eth.recent_logs`            | Transaction event logs from the last 30 minutes, \~128 blocks            |
| `eth.tokens`                 | A listing of token contracts                                             |
| `eth.token_transfers`        | Token transfers between addresses                                        |
| `eth.recent_token_transfers` | Token transfers between addresses from the last 30 minutes, \~128 blocks |
| `eth.token_mints`            | Token mints                                                              |
| `eth.recent_token_mints`     | Token mints from the last 30 minutes, \~128 blocks                       |
| `eth.contracts`              | A listing of all contracts                                               |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES
```

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE eth.blocks;
DESCRIBE eth.recent_blocks;
DESCRIBE eth.transactions;
DESCRIBE eth.recent_transactions;
DESCRIBE eth.logs;
DESCRIBE eth.recent_logs;
DESCRIBE eth.tokens;
DESCRIBE eth.token_mints;
DESCRIBE eth.recent_token_mints;
DESCRIBE eth.token_transfers;
DESCRIBE eth.recent_token_transfers;
DESCRIBE eth.contracts;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name            | Indexed Columns                                                                                |
| --------------------- | ---------------------------------------------------------------------------------------------- |
| `eth.blocks`          | `number` `hash` `timestamp`                                                                    |
| `eth.transactions`    | `block_number` `hash` `block_hash` `from_address` `to_address` `transaction_type`              |
| `eth.logs`            | `block_number` `log_index` `transaction_hash` `transaction_index` `block_hash` `address`       |
| `eth.receipts`        | `transaction_hash` `transaction_index` `block_hash` `block_number` `contract_address` `status` |
| `eth.token_transfers` | `block_number` `token_address` `from_address` `to_address` `transaction_hash`                  |
| `eth.token_mints`     | `block_number` `token_address` `to_address` `symbol` `name`                                    |

