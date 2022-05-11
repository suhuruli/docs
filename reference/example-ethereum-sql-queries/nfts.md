# NFTs

### NFT collections with the most airdrops of all time

**Typical query time**: <10 seconds

```sql
SELECT
    name,
    token_address,
    symbol,
    COUNT(*) AS num_mints,
    FROM_UNIXTIME(min(block_timestamp), 'YYYY-MM-dd') as first_minted,
    FROM_UNIXTIME(max(block_timestamp), 'YYYY-MM-dd') as last_minted
FROM eth.nft_airdrop_transfers
WHERE from_address='0x0000000000000000000000000000000000000000'
  AND name IS NOT NULL
GROUP BY token_address, name, symbol
HAVING COUNT(*)>1
ORDER BY COUNT(*) DESC
```

Run this query yourself using a [Kaggle notebook](https://www.kaggle.com/code/phillipleblanc/spice-xyz-nft-airdrops)
