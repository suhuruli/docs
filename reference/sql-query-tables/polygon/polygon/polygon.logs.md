---
description: SQL table schema for polygon.logs and polygon.recent_logs
---

# polygon.logs

Polygon Transaction event logs.

| Column Name         | Data Type         | Description                                           |
| ------------------- | ----------------- | ----------------------------------------------------- |
| `log_index`         | BIGINT            | The log index position in the block                   |
| `transaction_hash`  | CHARACTER VARYING | Hash of the transactions this log was created from.   |
| `transaction_index` | BIGINT            | The transactions index position log was created from  |
| `address`           | CHARACTER VARYING | Address from which this log originated                |
| `data`              | CHARACTER VARYING | One or more 32 Bytes non-indexed arguments of the log |
| `topics`            | ANY               | Array of indexed log arguments                        |
| `block_timestamp`   | BIGINT            | Timestamp of the block where this log was in          |
| `block_hash`        | CHARACTER VARYING | Hash of the block where this log was in               |
| `block_number`      | BIGINT            | The block number where this log was in                |
