---
description: SQL table schema for eth.traces and eth.recent_traces
---

# eth.traces

All Ethereum call frames executed during a transaction, also known as internal transactions.

| Column Name         | Data Type         |
| ------------------- | ----------------- |
| `transaction_hash`  | CHARACTER VARYING |
| `transaction_index` | BIGINT            |
| `from_address`      | CHARACTER VARYING |
| `to_address`        | CHARACTER VARYING |
| `value`             | DECIMAL           |
| `input`             | CHARACTER VARYING |
| `output`            | CHARACTER VARYING |
| `trace_type`        | CHARACTER VARYING |
| `call_type`         | CHARACTER VARYING |
| `reward_type`       | CHARACTER VARYING |
| `gas`               | BIGINT            |
| `gas_used`          | BIGINT            |
| `subtraces`         | BIGINT            |
| `trace_address`     | CHARACTER VARYING |
| `error`             | CHARACTER VARYING |
| `status`            | BIGINT            |
| `block_timestamp`   | BIGINT            |
| `block_number`      | BIGINT            |
| `block_hash`        | CHARACTER VARYING |
| `trace_id`          | CHARACTER VARYING |
