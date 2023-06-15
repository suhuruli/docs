---
description: SQL table schema for polygon.nft_transfers and polygon.recent_nft_transfers
---

# polygon.nft\_transfers

Polygon Transfers of erc721 & erc1155 NFTs. Does not include fungible tokens from erc1155 contracts.

|                    |                   |
| ------------------ | ----------------- |
| `token_address`    | CHARACTER VARYING |
| `from_address`     | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `token_id`         | CHARACTER VARYING |
| `block_number`     | BIGINT            |
| `block_timestamp`  | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
