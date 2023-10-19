# NFTs

### Recent NFT Airdrops

**Typical query time**: <60 seconds

```sql
SELECT nt.token_address, nt.token_id, nt.from_address, nt.to_address, nt.block_timestamp
FROM (
    SELECT * 
    FROM eth.recent_nft_transfers 
    WHERE block_timestamp > UNIX_TIMESTAMP() - 30*60
) AS nt
LEFT JOIN (
    SELECT block_number, hash
    FROM eth.recent_transactions
    WHERE "value" = 0
) AS t ON nt.block_number = t.block_number AND nt.transaction_hash = t.hash
```
