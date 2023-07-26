# Transactions

### Total Bitcoin Transferred in the last 30 minutes

Gets the total amount of bitcoin transferred within the last 30 minutes

**Typical query time**: 1 second

```sql
SELECT SUM(output_value) / 1e8 AS btc_transferred 
FROM btc.recent_transactions
```

Alternatively, use `UNIX_TIMESTAMP()` to specify your own time window:

```sql
SELECT SUM(output_value) / 1e8 AS btc_transferred 
FROM btc.transactions
WHERE block_timestamp > UNIX_TIMESTAMP() - 30*60 -- 30 minutes
```

### Recent Transactions with the Most Bitcoin Transferred

Gets the top 10 transactions from the last 30 minutes with the most amount of bitcoin transferred.

**Typical query time**: 1 second

```sql
SELECT output_value / 1e8 as btc_transferred, hash, block_number, block_timestamp, input_count, output_count, input_value, output_value, fee
FROM btc.recent_transactions
ORDER BY output_value DESC
LIMIT 10
```
