---
description: Goerli base type tables available to query via SQL
---

# Goerli

#### Goerli base type tables available to query

| Table Name                                                         | Description                                                                        |
| ------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| [`goerli.blocks`](core-tables/goerli.blocks.md)                    | Block headers                                                                      |
| [`goerli.recent_blocks`](core-tables/goerli.blocks.md)             | Block headers from the last 30 minutes, \~128 blocks                               |
| [`goerli.transactions`](core-tables/goerli.transactions.md)        | Block transactions                                                                 |
| [`goerli.recent_transactions`](core-tables/goerli.transactions.md) | Block transactions from the last 30 minutes, \~128 blocks                          |
| [`goerli.logs`](core-tables/goerli.logs.md)                        | Transaction event logs                                                             |
| [`goerli.recent_logs`](core-tables/goerli.logs.md)                 | Transaction event logs from the last 30 minutes, \~128 blocks                      |
| [`goerli.contracts`](core-tables/goerli.contracts.md)              | A listing of all contracts                                                         |
| [`goerli.traces`](core-tables/goerli.traces.md)                    | All call frames executed during a transaction, also known as internal transactions |
| [`goerli.recent_traces`](core-tables/goerli.traces.md)             | `goerli.traces` data from the last 30 minutes, \~128 blocks                        |
| [`goerli.withdrawals`](core-tables/goerli.withdrawals.md)          | Block withdrawals                                                                  |
| [`goerli.recent_withdrawals`](core-tables/goerli.withdrawals.md)   | Block withdrawals from the last 30 minutes, \~128 blocks                           |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN goerli
```

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE goerli.blocks;
DESCRIBE goerli.transactions;
DESCRIBE goerli.logs;
DESCRIBE goerli.recent_logs;
DESCRIBE goerli.contracts;
DESCRIBE goerli.traces;
DESCRIBE goerli.withdrawals;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name            | Indexed Columns                            |
| --------------------- | ------------------------------------------ |
| `goerli.blocks`       | `number` `timestamp` `hash`                |
| `goerli.transactions` | `block_number` `block_timestamp` `hash`    |
| `goerli.logs`         | `block_number` `block_timestamp` `address` |
| `goerli.contracts`    | `block_number` `block_timestamp` `address` |
| `goerli.traces`       | `block_number`                             |
| `goerli.withdrawals`  | `block_number`                             |
