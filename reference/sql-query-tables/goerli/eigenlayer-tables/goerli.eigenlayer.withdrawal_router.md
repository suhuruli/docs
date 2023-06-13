---
description: SQL table schema for goerli.eigenlayer.withdrawal_router
---

# goerli.eigenlayer.withdrawal\_router

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
DESCRIBE goerli.eigenlayer.withdrawal_router;
```
