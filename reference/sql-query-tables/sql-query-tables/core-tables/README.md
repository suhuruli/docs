---
description: Ethereum base type tables available to query via SQL
---

# Core Tables

#### Ethereum base type tables available to query

| Table Name                                       | Description                                                                        |
| ------------------------------------------------ | ---------------------------------------------------------------------------------- |
| [`eth.blocks`](eth.blocks.md)                    | Block headers                                                                      |
| [`eth.recent_blocks`](eth.blocks.md)             | Block headers from the last 30 minutes, \~128 blocks                               |
| [`eth.transactions`](eth.transactions.md)        | Block transactions                                                                 |
| [`eth.recent_transactions`](eth.transactions.md) | Block transactions from the last 30 minutes, \~128 blocks                          |
| [`eth.logs`](eth.logs.md)                        | Transaction event logs                                                             |
| [`eth.recent_logs`](eth.logs.md)                 | Transaction event logs from the last 30 minutes, \~128 blocks                      |
| [`eth.contracts`](eth.contracts.md)              | A listing of all contracts                                                         |
| [`eth.traces`](eth.traces.md)                    | All call frames executed during a transaction, also known as internal transactions |
| [`eth.recent_traces`](eth.traces.md)             | `eth.traces` data from the last 30 minutes, \~128 blocks                           |
| [`eth.withdrawals`](eth.withdrawals.md)          | Block withdrawals                                                                  |
| [`eth.recent_withdrawals`](eth.withdrawals.md)   | Block withdrawals from the last 30 minutes, \~128 blocks                           |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN eth
```

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE eth.blocks;
DESCRIBE eth.transactions;
DESCRIBE eth.logs;
DESCRIBE eth.recent_logs;
DESCRIBE eth.contracts;
DESCRIBE eth.traces;
DESCRIBE eth.withdrawals;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name         | Indexed Columns                            |
| ------------------ | ------------------------------------------ |
| `eth.blocks`       | `number` `timestamp` `hash`                |
| `eth.transactions` | `block_number` `block_timestamp` `hash`    |
| `eth.logs`         | `block_number` `block_timestamp` `address` |
| `eth.contracts`    | `block_number` `block_timestamp` `address` |
| `eth.traces`       | `block_number`                             |
| `eth.withdrawals`  | `block_number`                             |
