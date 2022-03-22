# Transactions

### All Transactions From/To an Address for 2021

Gets all of the transactions that occurred in 2021 involving a single address.

**Typical query time**: \~45 seconds

```sql
SELECT hash, block_number, nonce, from_address, to_address, "value", gas  
FROM eth.transactions 
WHERE (from_address = LOWER('0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045') 
   OR to_address = LOWER('0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045'))
   AND block_timestamp >= UNIX_TIMESTAMP('2021-01-01 00:00:00')
   AND block_timestamp <= UNIX_TIMESTAMP('2021-12-31 23:59:59')
```

### Largest Ethereum Transfer in 2021

Gets the transaction that involved the largest transfer of Ethereum in 2021.

**Typical query time**: <1 minute

```sql
SELECT "value" as max_eth_transferred, block_number, hash, TO_TIMESTAMP(block_timestamp) as block_timestamp
FROM eth.transactions 
WHERE block_timestamp >= UNIX_TIMESTAMP('2021-01-01 00:00:00')
   AND block_timestamp <= UNIX_TIMESTAMP('2021-12-31 23:59:59')
ORDER BY max_eth_transferred DESC
LIMIT 1
```
