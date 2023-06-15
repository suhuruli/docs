---
description: SQL table schema for polygon.nfts
---

# polygon.nfts

All Polygon NFTs from both ERC721 and ERC1155 contracts.

| Column Name  | Data Type         |
| ------------ | ----------------- |
| `address`    | CHARACTER VARYING |
| `token_id`   | CHARACTER VARYING |
| `name`       | CHARACTER VARYING |
| `symbol`     | CHARACTER VARYING |
| `is_erc721`  | BOOLEAN           |
| `is_erc1155` | BOOLEAN           |
