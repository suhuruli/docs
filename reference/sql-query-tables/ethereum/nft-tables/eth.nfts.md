---
description: SQL table schema for eth.nfts
---

# eth.nfts

All Ethereum NFTs from both ERC721 and ERC1155 contracts.

| Column Name  | Data Type         |
| ------------ | ----------------- |
| `address`    | CHARACTER VARYING |
| `token_id`   | CHARACTER VARYING |
| `name`       | CHARACTER VARYING |
| `symbol`     | CHARACTER VARYING |
| `is_erc721`  | BOOLEAN           |
| `is_erc1155` | BOOLEAN           |
