---
description: >-
  SQL table schema for "@Layr-Labs".goerli_eigenpod_validators and
  "@Layr-Labs".goerli_recent_eigenpod_validators
---

# goerli.eigenlayer.eigenpod\_validators

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
DESCRIBE goerli.eigenlayer.eigenpod_validators;
```
