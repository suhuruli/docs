# Gas & Fees

### Average Gas Used by Transactions per Block

Gets the average amount of gas used for a transaction within a single block.

**Typical query time**: <45 seconds

```sql
SELECT block_number, avg(receipt_gas_used) AS avg_gas_used
FROM eth.transactions 
GROUP BY block_number 
ORDER BY block_number DESC 
LIMIT 500
```

### Transaction Fees for Recent Blocks

Gets information about transactions fees for recent blocks, including the effective priority fee (defined as the difference between the block `baseFeePerGas` and the transaction `maxPriorityFeePerGas`) and the calculation of the fee in Ethereum.

**Typical query time**: \~1 minute

```sql
WITH recent_blocks AS (
    SELECT number, base_fee_per_gas AS block_base_fee_per_gas
    FROM eth.blocks
    ORDER BY number DESC
    LIMIT 500
)
SELECT recent_blocks.*,
       eth.transactions.transaction_index,
       eth.transactions.hash AS tx_hash,
       eth.transactions.gas,
       eth.transactions.max_priority_fee_per_gas,
       eth.transactions.gas_price,
       eth.transactions.gas_price - recent_blocks.block_base_fee_per_gas AS effective_priority_fee,
       eth.transactions.gas * (eth.transactions.gas_price / 1e18) AS fee_in_eth
FROM recent_blocks INNER JOIN eth.transactions ON 
  eth.transactions.block_number = recent_blocks.number
ORDER BY recent_blocks.number DESC, transaction_index ASC
```

### Total Transaction Fees in Ethereum Per Block

For recent blocks, calculate the total amount of Ethereum paid in fees for all of the transactions in that block.

**Typical query time**: <15 seconds

```sql
WITH recent_blocks AS (
    SELECT number, base_fee_per_gas AS block_base_fee_per_gas
    FROM eth.blocks
    ORDER BY number DESC
    LIMIT 500
)
SELECT recent_blocks.number,
       sum(eth.transactions.gas * (eth.transactions.gas_price / 1e18)) AS fee_in_eth
FROM recent_blocks INNER JOIN 
  eth.transactions ON eth.transactions.block_number = recent_blocks.number
GROUP BY recent_blocks.number
ORDER BY number DESC
```
