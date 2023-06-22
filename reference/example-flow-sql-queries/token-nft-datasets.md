# Token/NFT Datasets

### NFTs with metadata

```sql
SELECT id, name, description, thumbnail_url, external_url, collection_name, serial
FROM flow.nfts
WHERE name IS NOT NULL
LIMIT 10
```

### Get the Thumbnail URL of a specific NFT

The `id` of an NFT is constructed as:

`A.{collection_address}.{collection_name}.{serial}`

```sql
SELECT thumbnail_url
FROM flow.nfts
WHERE id = 'A.329feb3ab062d289.UFC_NFT.2266641'
```

### Get the transfers of a specific NFT

```sql
SELECT *
FROM flow.nft_transfers
WHERE nft_id = 'A.329feb3ab062d289.UFC_NFT.2266641'
LIMIT 10
```

### Get the current owners of specific NFTs

```sql
WITH ranked_transfers AS (
    SELECT 
      nft_id, 
      to_address, 
      ROW_NUMBER() OVER (
        PARTITION BY nft_id ORDER BY block_height DESC
      ) AS rn
    FROM flow.nft_transfers
    WHERE nft_id IN 
      ('A.329feb3ab062d289.UFC_NFT.2266641', 
       'A.34ac358b9819f79d.NFTKred.65327539198951425')
)
SELECT to_address as current_owner, nft_id
FROM ranked_transfers WHERE rn = 1
```

### Get the value of recently transferred fungible tokens

```sql
SELECT SUM("value") AS total_transferred, token_name
FROM flow.recent_token_transfers
GROUP BY token_name
```
