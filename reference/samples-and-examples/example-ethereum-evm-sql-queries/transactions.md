# Transactions

### Popular Ethereum Contracts

Get the 10 most used contracts over the last month

**Typical query time**: \~60 seconds

```sql
SELECT 
  to_address,
  COUNT(*) AS transaction_count
FROM eth.transactions
WHERE block_timestamp > UNIX_TIMESTAMP(NOW()) - 2592000
GROUP BY to_address
ORDER BY transaction_count DESC
LIMIT 10;

```
