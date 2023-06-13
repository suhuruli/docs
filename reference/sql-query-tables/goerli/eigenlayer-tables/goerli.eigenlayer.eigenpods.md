---
description: SQL table schema for goerli.eigenpods
---

# goerli.eigenlayer.eigenpods

| Column Name             | Description       |
| ----------------------- | ----------------- |
| `withdrawal_credential` | CHARACTER VARYING |
| `pod_owner`             | CHARACTER VARYING |
| `transaction_hash`      | CHARACTER VARYING |
| `log_index`             | BIGINT            |
| `block_hash`            | CHARACTER VARYING |
| `block_timestamp`       | BIGINT            |
| \`block\_number         | BIGINT            |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE goerli.eigenlayer.eigenpods;
```
