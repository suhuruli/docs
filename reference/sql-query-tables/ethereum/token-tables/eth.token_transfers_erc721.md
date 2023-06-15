---
description: SQL table schema for eth.token_transfers_erc721
---

# eth.token\_transfers\_erc721

Ethereum Token tables ERC-721 token transfers (NFTs).

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `token_address`    | CHARACTER VARYING |
| `from_address`     | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `token_id`         | CHARACTER VARYING |
| `value`            | CHARACTER VARYING |
| `value_hex`        | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `log_index`        | BIGINT            |
| `block_timestamp`  | BIGINT            |
| `block_number`     | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
