# Gas & Fees

### Average Gas Used by Transactions per Block

Gets the average amount of gas used for a transaction within a single block.

**Typical query time**: <10 seconds

```sql
SELECT block_number, avg(receipt_gas_used) AS avg_gas_used
FROM eth.transactions 
WHERE block_timestamp > UNIX_TIMESTAMP()-4*60*60 -- only consider transactions from 4 hours ago
GROUP BY block_number 
ORDER BY block_number DESC 
LIMIT 500
```

### Transaction Fees for Recent Blocks

Gets information about transactions fees for recent blocks, including the effective priority fee (defined as the difference between the block `baseFeePerGas` and the transaction `maxPriorityFeePerGas`) and the calculation of the fee in Ethereum.

**Typical query time**: \~1 minute

```sql
SELECT eth.recent_blocks.*,
       transaction_index,
       eth.recent_transactions.hash AS tx_hash,
       gas,
       max_priority_fee_per_gas,
       gas_price,
       gas_price - recent_blocks.base_fee_per_gas AS effective_priority_fee,
       gas * (gas_price / 1e18) AS fee_in_eth
FROM recent_blocks INNER JOIN eth.recent_transactions ON 
  eth.recent_transactions.block_number = recent_blocks.number
ORDER BY recent_blocks.number DESC, transaction_index ASC
LIMIT 500
```

### Total Transaction Fees in Ethereum Per Block

For recent blocks, calculate the total amount of Ethereum paid in fees for all of the transactions in that block.

**Typical query time**: <15 seconds

```sql
SELECT eth.recent_blocks.number,
       sum(eth.recent_transactions.gas * (eth.recent_transactions.gas_price / 1e18)) AS fee_in_eth
FROM eth.recent_blocks INNER JOIN 
  eth.recent_transactions ON eth.recent_transactions.block_number = recent_blocks.number
GROUP BY recent_blocks.number
ORDER BY number DESC
```
