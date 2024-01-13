---
description: Holesky base type tables available to query via SQL
---

# Core Tables

#### Holesky base type tables available to query

| Table Name                                               | Description                                                                        |
| -------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| [`holesky.blocks`](holesky.blocks.md)                    | Block headers                                                                      |
| [`holesky.recent_blocks`](holesky.blocks.md)             | Block headers from the last 30 minutes, \~128 blocks                               |
| [`holesky.transactions`](holesky.transactions.md)        | Block transactions                                                                 |
| [`holesky.recent_transactions`](holesky.transactions.md) | Block transactions from the last 30 minutes, \~128 blocks                          |
| [`holesky.logs`](holesky.logs.md)                        | Transaction event logs                                                             |
| [`holesky.recent_logs`](holesky.logs.md)                 | Transaction event logs from the last 30 minutes, \~128 blocks                      |
| [`holesky.contracts`](holesky.contracts.md)              | A listing of all contracts                                                         |
| [`holesky.traces`](holesky.traces.md)                    | All call frames executed during a transaction, also known as internal transactions |
| [`holesky.recent_traces`](holesky.traces.md)             | `holesky.traces` data from the last 30 minutes, \~128 blocks                       |
| [`holesky.withdrawals`](holesky.withdrawals.md)          | Block withdrawals                                                                  |
| [`holesky.recent_withdrawals`](holesky.withdrawals.md)   | Block withdrawals from the last 30 minutes, \~128 blocks                           |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN holesky
```

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE holesky.blocks;
DESCRIBE holesky.transactions;
DESCRIBE holesky.logs;
DESCRIBE holesky.recent_logs;
DESCRIBE holesky.contracts;
DESCRIBE holesky.traces;
DESCRIBE holesky.withdrawals;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name             | Indexed Columns                            |
| ---------------------- | ------------------------------------------ |
| `holesky.blocks`       | `number` `timestamp` `hash`                |
| `holesky.transactions` | `block_number` `block_timestamp` `hash`    |
| `holesky.logs`         | `block_number` `block_timestamp` `address` |
| `holesky.contracts`    | `block_number` `block_timestamp` `address` |
| `holesky.traces`       | `block_number`                             |
| `holesky.withdrawals`  | `block_number`                             |
