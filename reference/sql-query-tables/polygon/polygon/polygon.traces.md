---
description: SQL table schema for polygon.traces and polygon.recent_traces
---

# polygon.traces

All Polygon call frames executed during a transaction, also known as internal transactions.

| Column Name         | Data Type         | Description                                                    |
| ------------------- | ----------------- | -------------------------------------------------------------- |
| `transaction_hash`  | CHARACTER VARYING | Transaction hash where the trace was in                        |
| `transaction_index` | BIGINT            | Transaction index position in the block where the trace was in |
| `from_address`      | CHARACTER VARYING | Address of the sender                                          |
| `to_address`        | CHARACTER VARYING | Address of the receiver                                        |
| `value`             | CHARACTER VARYING | Value transferred in MATIC                                     |
| `input`             | CHARACTER VARYING | Optional field to include arbitrary data                       |
| `output`            | CHARACTER VARYING | The output of the message call                                 |
| `trace_type`        | CHARACTER VARYING | One of call, create, daofork, genesis, reward, suicide         |
| `call_type`         | CHARACTER VARYING | One of call, callcode, delegatecall, staticcall                |
| `reward_type`       | CHARACTER VARYING | One of block, uncle                                            |
| `gas`               | BIGINT            | Gas provided in the message call                               |
| `gas_used`          | BIGINT            | Gas used by the message call                                   |
| `subtraces`         | BIGINT            | Number of subtraces                                            |
| `trace_address`     | CHARACTER VARYING | List of trace addresses                                        |
| `error`             | CHARACTER VARYING | Error message when the message call is failed                  |
| `status`            | BIGINT            | 1 (success) / 0 (failure)                                      |
| `block_timestamp`   | BIGINT            | Block timestamp where the trace was in                         |
| `block_number`      | BIGINT            | Block number where the trace was in                            |
| `block_hash`        | CHARACTER VARYING | Block hash where the trace was in                              |
| `trace_id`          | CHARACTER VARYING | Unique identifier of the trace                                 |
