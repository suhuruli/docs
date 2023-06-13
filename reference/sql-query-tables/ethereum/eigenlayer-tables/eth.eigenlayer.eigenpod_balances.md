---
description: SQL table schema for eth.eigenlayer.eigenpod_balances
---

# eth.eigenlayer.eigenpod\_balances

| Column Name       | Description       |
| ----------------- | ----------------- |
| `balance_gwei`    | DECIMAL           |
| `balance_hex`     | CHARACTER VARYING |
| `balance_delta`   | DECIMAL           |
| `block_timestamp` | BIGINT            |
| `block_number`    | BIGINT            |
| `block_hash`      | CHARACTER VARYING |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE eth.eigenlayer.eigenpod_balances;
```
