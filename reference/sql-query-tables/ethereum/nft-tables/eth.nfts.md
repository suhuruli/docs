---
description: SQL table schema for eth.nfts
---

# eth.nfts

All Ethereum NFTs from both ERC721 and ERC1155 contracts.

| Column Name  | Data Type         | Description                                                                     |
| ------------ | ----------------- | ------------------------------------------------------------------------------- |
| `address`    | CHARACTER VARYING | The contract address of this NFT.                                               |
| `token_id`   | CHARACTER VARYING | The unique, opaque identifier of this specific NFT mint.                        |
| `name`       | CHARACTER VARYING | The human-readable name of this NFT, eg. "Gods Unchained Cards".                |
| `symbol`     | CHARACTER VARYING | The human-readable symbol for this NFT, eg. CARD.                               |
| `is_erc721`  | BOOLEAN           | True if Spice considers this token contract to conform to the ERC721 standard.  |
| `is_erc1155` | BOOLEAN           | True if Spice considers this token contract to conform to the ERC1155 standard. |

