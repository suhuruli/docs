---
description: SQL table schema for eth.nft_transfers
---

# eth.nft\_transfers

All Ethereum erc721 contracts & subset of erc1155 contracts that contain NFTs.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `token_address`    | CHARACTER VARYING |
| `from_address`     | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `token_id`         | CHARACTER VARYING |
| `block_number`     | BIGINT            |
| `block_timestamp`  | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
