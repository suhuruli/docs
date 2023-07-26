---
description: SQL table schema for polygon.transactions and polygon.recent_transactions
---

# polygon.transactions

Polygon Block transactions.

| Column Name                   | Data Type         | Description                                                                  |
| ----------------------------- | ----------------- | ---------------------------------------------------------------------------- |
| `hash`                        | CHARACTER VARYING | Transaction hash                                                             |
| `nonce`                       | BIGINT            | Transaction nonce                                                            |
| `transaction_index`           | BIGINT            | Index position of the transaction in the block                               |
| `from_address`                | CHARACTER VARYING | The address of the sender                                                    |
| `to_address`                  | CHARACTER VARYING | The address of the receiver                                                  |
| `value`                       | DECIMAL           | Amount of MATIC transferred in the transaction                               |
| `gas`                         | BIGINT            | The maximum amount of gas can be consumed by the transaction                 |
| `gas_price`                   | BIGINT            | The amount user willing to pay for a unit of gas                             |
| `input`                       | CHARACTER VARYING | Optional field to include arbitrary data                                     |
| `receipt_cumulative_gas_used` | BIGINT            | The total amount of gas used when this transaction was executed in the block |
| `receipt_gas_used`            | BIGINT            | The amount of gas used by this specific transaction alone                    |
| `receipt_contract_address`    | CHARACTER VARYING | The contract address created, if the transaction was a contract creation     |
| `receipt_root`                | CHARACTER VARYING | The root hash of receipt trie                                                |
| `receipt_status`              | BIGINT            | 0/1 value representing the state (failure/success) of a transaction          |
| `block_timestamp`             | BIGINT            | Unix timestamp of the block where the transaction is in                      |
| `block_number`                | BIGINT            | The block number of the block where the transaction is in                    |
| `block_hash`                  | CHARACTER VARYING | Block hash of the block where the transaction is in                          |
