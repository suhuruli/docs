---
description: Goerli base type tables available to query via SQL
---

# Goerli

#### Goerli base type tables available to query

| Table Name                   | Description                                                                        |
| ---------------------------- | ---------------------------------------------------------------------------------- |
| `goerli.blocks`              | Block headers                                                                      |
| `goerli.recent_blocks`       | Block headers from the last 30 minutes, \~128 blocks                               |
| `goerli.transactions`        | Block transactions                                                                 |
| `goerli.recent_transactions` | Block transactions from the last 30 minutes, \~128 blocks                          |
| `goerli.logs`                | Transaction event logs                                                             |
| `goerli.recent_logs`         | Transaction event logs from the last 30 minutes, \~128 blocks                      |
| `goerli.contracts`           | A listing of all contracts                                                         |
| `goerli.traces`              | All call frames executed during a transaction, also known as internal transactions |
| `goerli.recent_traces`       | `goerli.traces` data from the last 30 minutes, \~128 blocks                        |
| `goerli.withdrawals`         | Block withdrawals                                                                  |
| `goerli.recent_withdrawals`  | Block withdrawals from the last 30 minutes, \~128 blocks                           |

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
