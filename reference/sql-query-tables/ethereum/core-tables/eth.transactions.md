---
description: SQL table schema for eth.transactions and eth.recent_transactions
---

# eth.transactions

Ethereum Block transactions. For more [details](https://ethereum.org/en/developers/docs/transactions/).

| Column Name                   | Data Type         | Description                                                                                       |
| ----------------------------- | ----------------- | ------------------------------------------------------------------------------------------------- |
| `hash`                        | CHARACTER VARYING | The transaction's hash                                                                            |
| `nonce`                       | BIGINT            | Incremental account transaction number                                                            |
| `transaction_index`           | BIGINT            | Index of transaction in block                                                                     |
| `from_address`                | CHARACTER VARYING | Address of sender, signing transaction                                                            |
| `to_address`                  | CHARACTER VARYING | The receiving address, a contract or externally-owned.                                            |
| `value`                       | DECIMAL           | The amount of Wei to transfer.                                                                    |
| `gas`                         | BIGINT            | The maximum allowed gas for the transaction.                                                      |
| `gas_price`                   | BIGINT            | The price the sender is willing to pay per unit of gas                                            |
| `input`                       | CHARACTER VARYING | optional, arbitrary input data                                                                    |
| `receipt_cumulative_gas_used` | BIGINT            | Total amount of gas used in the block, inclusive of this transaction                              |
| `receipt_gas_used`            | BIGINT            | Gas used in this transaction                                                                      |
| `receipt_contract_address`    | CHARACTER VARYING | Contract address, if created                                                                      |
| `receipt_root`                | CHARACTER VARYING | Pre-byzantine, the post-transaction state root.                                                   |
| `receipt_status`              | BIGINT            | Status, from the receipt, indicating either success (1) or failure (0).                           |
| `block_timestamp`             | BIGINT            | Unix time when the block including this transaction was mined.                                    |
| `block_number`                | BIGINT            | The number of the block including this transaction                                                |
| `block_hash`                  | CHARACTER VARYING | The hash of the block including this transaction                                                  |
| `max_fee_per_gas`             | BIGINT            | The maximum allowed fee per gas for the transaction.                                              |
| `max_priority_fee_per_gas`    | BIGINT            | The maximum allowed priority fee per gas for the transaction.                                     |
| `transaction_type`            | BIGINT            | The transactionType id                                                                            |
| `receipt_effective_gas_price` | BIGINT            | Effective/cumulative gas price. Minimum of the max gas price, or the base fee plus inclusion fee. |

