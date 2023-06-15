---
description: SQL table schema for polygon.transactions and polygon.recent_transactions
---

# polygon.transactions

Polygon Block transactions.

| Column Name                   | Data Type         |
| ----------------------------- | ----------------- |
| `hash`                        | CHARACTER VARYING |
| `nonce`                       | BIGINT            |
| `transaction_index`           | BIGINT            |
| `from_address`                | CHARACTER VARYING |
| `to_address`                  | CHARACTER VARYING |
| `value`                       | DECIMAL           |
| `gas`                         | BIGINT            |
| `gas_price`                   | BIGINT            |
| `input`                       | CHARACTER VARYING |
| `receipt_cumulative_gas_used` | BIGINT            |
| `receipt_gas_used`            | BIGINT            |
| `receipt_contract_address`    | CHARACTER VARYING |
| `receipt_root`                | CHARACTER VARYING |
| `receipt_status`              | BIGINT            |
| `block_timestamp`             | BIGINT            |
| `block_number`                | BIGINT            |
| `block_hash`                  | CHARACTER VARYING |
