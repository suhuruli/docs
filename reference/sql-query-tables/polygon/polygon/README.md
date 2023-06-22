---
description: Polygon base type tables available to query via SQL
---

# Core Tables

As a blockchain compatible with the Ethereum Virtual Machine (EVM) standard, the Polygon tables are very similar to the [Ethereum](../../ethereum/) tables in structure.

#### Polygon base type tables available to query

| Table Name                                               | Description                                                                        |
| -------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| [`polygon.blocks`](polygon.blocks.md)                    | Block headers                                                                      |
| [`polygon.recent_blocks`](polygon.blocks.md)             | Block headers from the last 30 minutes, \~900 blocks                               |
| [`polygon.transactions`](polygon.transactions.md)        | Block transactions                                                                 |
| [`polygon.recent_transactions`](polygon.transactions.md) | Block transactions from the last 30 minutes, \~900 blocks                          |
| [`polygon.logs`](polygon.logs.md)                        | Transaction event logs                                                             |
| [`polygon.recent_logs`](polygon.logs.md)                 | Transaction event logs from the last 30 minutes, \~900 blocks                      |
| [`polygon.contracts`](polygon.contracts.md)              | A listing of all contracts                                                         |
| [`polygon.traces`](polygon.traces.md)                    | All call frames executed during a transaction, also known as internal transactions |
| [`polygon.recent_traces`](polygon.traces.md)             | `polygon.traces` data from the last 30 minutes, \~900 blocks                       |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN polygon
```

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE polygon.blocks;
DESCRIBE polygon.transactions;
DESCRIBE polygon.logs;
DESCRIBE polygon.contracts;
DESCRIBE polygon.traces;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name             | Indexed Columns                            |
| ---------------------- | ------------------------------------------ |
| `polygon.blocks`       | `number` `timestamp`                       |
| `polygon.transactions` | `block_number` `hash` `block_timestamp`    |
| `polygon.logs`         | `block_number` `address` `block_timestamp` |
| `polygon.contracts`    | `block_number` `block_timestamp`           |
| `polygon.traces`       | `block_number` `block_timestamp`           |
