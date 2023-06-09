---
description: Bitcoin data tables available in SQL query
---

# Bitcoin

#### Bitcoin base type tables available to query

| Table Name                                                      | Description                                                    |
| --------------------------------------------------------------- | -------------------------------------------------------------- |
| [`btc.blocks`](btc.blocks.md)                                   | Block headers                                                  |
| [`btc.recent_blocks`](btc.blocks.md)                            | Block headers from the last 30 minutes, \~3 blocks             |
| [`btc.transactions`](btc.transactions.md)                       | Block transactions                                             |
| [`btc.recent_transactions`](btc.transactions.md)                | Block transactions from the last 30 minutes, \~3 blocks        |
| [`btc.transaction_inputs`](btc.transaction\_inputs.md)          | All inputs to transactions                                     |
| [`btc.recent_transaction_inputs`](btc.transaction\_inputs.md)   | Inputs to transactions from the last 30 minutes, \~3 blocks    |
| [`btc.transaction_outputs`](btc.transaction\_outputs.md)        | All outputs from transactions                                  |
| [`btc.recent_transaction_outputs`](btc.transaction\_outputs.md) | Outputs from transactions from the last 30 minutes, \~3 blocks |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN btc
```

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE btc.blocks;
DESCRIBE btc.transactions;
DESCRIBE btc.transaction_inputs;
DESCRIBE btc.transaction_outputs;
```

#### Improving query performance - indexed columns

| Table Name                | Indexed Columns                  |
| ------------------------- | -------------------------------- |
| `btc.blocks`              | `number` `timestamp`             |
| `btc.transactions`        | `block_number` `block_timestamp` |
| `btc.transaction_inputs`  | `block_number` `block_timestamp` |
| `btc.transaction_outputs` | `block_number` `block_timestamp` |
