# NFTs

### Recent NFT Transfers

Transfers of NFTs that conform to both ERC721 and ERC1155 token standards.

```sql
SELECT * FROM eth.recent_nft_transfers
ORDER BY block_number DESC, token_address, token_id
LIMIT 10
```

### All BAYC NFTs

Get all Bored Ape Yacht Club NFTs.

```sql
SELECT * FROM eth.nfts
WHERE address = '0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d' -- BAYC
ORDER BY CAST(token_id AS NUMERIC)
```

### Current owners of all BAYC NFTs

Get the current owners of all Bored Ape Yacht Club NFTs.

```sql
SELECT * FROM eth.nft_owners
WHERE token_address = '0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d' -- BAYC
ORDER BY CAST(token_id AS NUMERIC)
```

### Number of smart contracts with NFTs

Returns how many NFT smart contracts exist

```sql
SELECT COUNT(*) as "num_contracts"
FROM eth.nft_contracts
```

### Recent NFT Airdrops

**Typical query time**: <10 seconds

```sql
SELECT * 
FROM eth.recent_nft_airdrop_transfers 
ORDER BY block_number DESC
LIMIT 10
```
