---
description: SQL table schema for goerli.traces and goerli.recent_traces
---

# goerli.traces

All Goerli call frames executed during a transaction, also known as internal transactions.

| Column Name         | Data Type         | Description                                                             |
| ------------------- | ----------------- | ----------------------------------------------------------------------- |
| `transaction_hash`  | CHARACTER VARYING | Hash of the transaction this trace belongs to.                          |
| `transaction_index` | BIGINT            | The position of the trace's transaction in its block.                   |
| `from_address`      | CHARACTER VARYING | Address of sender, signing transaction                                  |
| `to_address`        | CHARACTER VARYING | The receiving address, a contract or externally-owned.                  |
| `value`             | DECIMAL           | The amount of Wei sent in the transaction.                              |
| `input`             | CHARACTER VARYING | Optional, arbitrary input data of the transaction                       |
| `output`            | CHARACTER VARYING | The data returned by the contract function call.                        |
| `trace_type`        | CHARACTER VARYING | Indicates the type of trace represented.                                |
| `call_type`         | CHARACTER VARYING | For traces representing EVM  call operations, the type of call.         |
| `reward_type`       | CHARACTER VARYING | For traces rewarding ether, indicate the type of reward.                |
| `gas`               | BIGINT            | The maximum allowed gas for the transaction.                            |
| `gas_used`          | BIGINT            | Gas used in this transaction                                            |
| `subtraces`         | BIGINT            | The count of subtraces triggered by this trace.                         |
| `trace_address`     | CHARACTER VARYING | Trace addresses                                                         |
| `error`             | CHARACTER VARYING | An error message, if the trace resulted in one.                         |
| `status`            | BIGINT            | Status, from the receipt, indicating either success (1) or failure (0). |
| `block_timestamp`   | BIGINT            | Unix time when the block including this transaction was mined.          |
| `block_number`      | BIGINT            | The number of the block including this transaction                      |
| `block_hash`        | CHARACTER VARYING | The hash of the block including this transaction                        |
| `trace_id`          | CHARACTER VARYING | Unique identifier of the trace.                                         |
