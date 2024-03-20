# Blobs

Example queries that use the [Ethereum EIP-4844: Shard Blob Transactions](https://eips.ethereum.org/EIPS/eip-4844) information.

### Blob Transaction Fees in the last 4 hours&#x20;

Total fee and fee per single blob for [Blob Transactions](https://eips.ethereum.org/EIPS/eip-4844) in the last 4 hrs&#x20;

**Typical query time**: <5 seconds

```sql
SELECT 
    block_number, 
    block_timestamp, 
    ARRAY_SIZE(blob_versioned_hashes) as blobs_count,
    gas * (receipt_effective_gas_price / 1e18) as fee_in_eth,
    fee_in_eth/blobs_count as fee_in_eth_per_blob
from  eth.transactions
where transaction_type = 3 and block_timestamp > UNIX_TIMESTAMP()-4*60*60
order by block_timestamp DESC
```

### Maximum Fee the Sender Was Willing To Pay Per Blob Gas&#x20;

Maximum fee the sender was willing to pay per blob gas in [Blob Transaction](https://eips.ethereum.org/EIPS/eip-4844) in the last 30 minutes

**Typical query time**: <1-3 seconds

```sql
SELECT block_number, max_fee_per_blob_gas from eth.recent_transactions
where transaction_type = 3
order by max_fee_per_blob_gas desc
```

### Average Gas Used Per Blob&#x20;

Calculated gas used per blob in [Blob Transactions](https://eips.ethereum.org/EIPS/eip-4844) in the last 4 hrs.

**Typical query time**: <5 seconds

```sql
SELECT 
       eth.blocks.number, 
       blob_gas_used,
       sum(ARRAY_SIZE(eth.transactions.blob_versioned_hashes)) AS blobs_count,
       blob_gas_used/blobs_count as avg_gas_per_blob
FROM eth.blocks INNER JOIN 
  eth.transactions ON eth.transactions.block_number = blocks.number
WHERE transaction_type = 3 and block_timestamp > UNIX_TIMESTAMP()-4*60*60
GROUP BY blocks.number, blob_gas_used
ORDER BY number DESC
```
