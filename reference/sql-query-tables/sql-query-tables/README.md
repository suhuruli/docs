---
description: Ethereum base type tables available to query via SQL
---

# Ethereum

#### Ethereum base type tables available to query

| Table Name                | Description                                                                        |
| ------------------------- | ---------------------------------------------------------------------------------- |
| `eth.blocks`              | Block headers                                                                      |
| `eth.recent_blocks`       | Block headers from the last 30 minutes, \~128 blocks                               |
| `eth.transactions`        | Block transactions                                                                 |
| `eth.recent_transactions` | Block transactions from the last 30 minutes, \~128 blocks                          |
| `eth.logs`                | Transaction event logs                                                             |
| `eth.recent_logs`         | Transaction event logs from the last 30 minutes, \~128 blocks                      |
| `eth.contracts`           | A listing of all contracts                                                         |
| `eth.traces`              | All call frames executed during a transaction, also known as internal transactions |
| `eth.recent_traces`       | `eth.traces` data from the last 30 minutes, \~128 blocks                           |

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
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name         | Indexed Columns             |
| ------------------ | --------------------------- |
| `eth.blocks`       | `number` `hash` `timestamp` |
| `eth.transactions` | `block_number` `hash`       |
| `eth.logs`         | `block_number`              |
| `eth.contracts`    | `address`                   |
| `eth.traces`       | `block_number`              |
