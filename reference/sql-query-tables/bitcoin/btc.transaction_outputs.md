---
description: SQL table schema for btc.transaction_outputs
---

# btc.transaction\_outputs

All Bitcoin outputs from transactions.

| Column Name        | Data Type         | Description                                                         |
| ------------------ | ----------------- | ------------------------------------------------------------------- |
| `transaction_hash` | CHARACTER VARYING | The hash of this transaction                                        |
| `index`            | BIGINT            | 0-indexed number of an input within a transaction                   |
| `script_asm`       | CHARACTER VARYING | Symbolic representation of the bitcoins script language op-codes    |
| `script_hex`       | CHARACTER VARYING | Hexadecimal representation of the bitcoins script language op-codes |
| `type`             | CHARACTER VARYING | The address type of the output                                      |
| `addresses`        | ANY               | Addresses which own this output                                     |
| `value`            | DECIMAL           | The value in base currency attached to this output                  |
| `block_number`     | BIGINT            | Block number                                                        |
| `block_hash`       | CHARACTER VARYING | Block hash                                                          |
| `block_timestamp`  | BIGINT            | Block creation timestamp                                            |
