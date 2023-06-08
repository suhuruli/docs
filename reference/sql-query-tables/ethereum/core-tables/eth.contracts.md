---
description: SQL table schema for eth.contracts
---

# eth.contracts

| Column Name          | Data Type         |
| -------------------- | ----------------- |
| `address`            | CHARACTER VARYING |
| `bytecode`           | CHARACTER VARYING |
| `function_sighashes` | ANY               |
| `block_number`       | BIGINT            |
| `block_hash`         | CHARACTER VARYING |
| `block_timestamp`    | BIGINT            |
| `is_erc20`           | BOOLEAN           |
| `is_erc721`          | BOOLEAN           |
| `is_erc1155`         | BOOLEAN           |
| `erc20_confidence`   | DECIMAL           |
| `erc721_confidence`  | DECIMAL           |
| `erc1155_confidence` | DECIMAL           |
