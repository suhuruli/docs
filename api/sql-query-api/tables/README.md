---
description: Ethereum base type tables available to query via SQL
---

# Tables



#### Ethereum base type tables available to query

| **Table Name**        | **Description**                          |
| --------------------- | ---------------------------------------- |
| `eth.blocks`          | Block headers                            |
| `eth.transactions`    | Block transactions                       |
| `eth.receipts`        | Transaction receipts                     |
| `eth.logs`            | Transaction event logs                   |
| `eth.token_transfers` | Token transfers between addresses        |
| `eth.tokens`          | A listing of token contracts             |
| `eth.contracts`       | A listing of all contracts               |
| `eth.contracts_oss`   | A listing of known open-source contracts |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES
```

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE eth.blocks;
DESCRIBE eth.transactions;
DESCRIBE eth.receipts;
DESCRIBE eth.logs;
DESCRIBE eth.token_transfers;
DESCRIBE eth.tokens;
DESCRIBE eth.contracts;
DESCRIBE eth.contracts_oss;
```
