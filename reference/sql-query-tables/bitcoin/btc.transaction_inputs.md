---
description: SQL table schema for btc.transaction_inputs and btc.recent_transaction_inputs
---

# btc.transaction\_inputs

All  Bitcoin inputs to transactions.

| Column Name              | Data Type         | Description                                                                                                                                                          |
| ------------------------ | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `transaction_hash`       | CHARACTER VARYING | The hash of the transaction                                                                                                                                          |
| `index`                  | BIGINT            | 0 indexed number of an input within a transaction                                                                                                                    |
| `spent_transaction_hash` | CHARACTER VARYING | The hash of the transaction which contains the output that this input spends                                                                                         |
| `spent_output_index`     | BIGINT            | The index of the output this input spends                                                                                                                            |
| `script_asm`             | CHARACTER VARYING | Symbolic representation of the bitcoins script language op-codes                                                                                                     |
| `script_hex`             | CHARACTER VARYING | Hexadecimal representation of the bitcoins script language op-codes                                                                                                  |
| `sequence`               | BIGINT            | A number intended to allow unconfirmed time-locked transactions to be updated before being finalized; not currently used except to disable locktime in a transaction |
| `addresses`              | ANY               | Addresses which own the spent output                                                                                                                                 |
| `value`                  | DECIMAL           | The value in base currency attached to the spent output                                                                                                              |
| `block_number`           | BIGINT            | Block number                                                                                                                                                         |
| `block_hash`             | CHARACTER VARYING | Block hash                                                                                                                                                           |
| `block_timestamp`        | BIGINT            | Block creation timestamp                                                                                                                                             |
