---
description: Ethereum base type tables available to query via SQL
---

# SQL Query Tables

#### Ethereum base type tables available to query

| `eth.blocks`          | Block headers                     |
| --------------------- | --------------------------------- |
| `eth.recent_blocks`   | The latest 100 block headers      |
| `eth.transactions`    | Block transactions                |
| `eth.receipts`        | Transaction receipts              |
| `eth.logs`            | Transaction event logs            |
| `eth.tokens`          | A listing of token contracts      |
| `eth.token_transfers` | Token transfers between addresses |
| `eth.token_mints`     | Token mints                       |
| `eth.contracts`       | A listing of all contracts        |

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
DESCRIBE eth.receipts;
DESCRIBE eth.logs;
DESCRIBE eth.tokens;
DESCRIBE eth.token_mints;
DESCRIBE eth.token_transfers;
DESCRIBE eth.contracts;
```
