---
description: SQL table schema for eth.logs and eth.recent_logs
---

# eth.logs

Ethereum Transaction event logs.

| Column Name         | Data Type         | Description                                         |
| ------------------- | ----------------- | --------------------------------------------------- |
| `log_index`         | BIGINT            | Position of log in its block.                       |
| `transaction_hash`  | CHARACTER VARYING | Hash of transaction for which this log derives from |
| `transaction_index` | BIGINT            | The position of the transaction in its block.       |
| `address`           | CHARACTER VARYING | Address of the transaction that produced the log    |
| `data`              | CHARACTER VARYING | Non-indexed argument for the log (dependent on      |
| `topics`            | ANY               | Array of 32 byte data. Order-dependent.             |
| `block_timestamp`   | BIGINT            | The timestamp of the block this log is within.      |
| `block_hash`        | CHARACTER VARYING | The hash of the block this log is within.           |
| `block_number`      | BIGINT            | The block number this log is within.                |
