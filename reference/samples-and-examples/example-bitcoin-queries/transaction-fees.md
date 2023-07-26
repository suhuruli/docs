# Transaction Fees

### Total Transaction Fees Per Block

Gets information about the total transaction fees by block for recent blocks.

**Typical query time**: 1 second

```sql
SELECT SUM(fee) / 1e8 AS fee_in_btc, 
       block_number, 
       TO_TIMESTAMP(block_timestamp) AS block_timestamp
FROM btc.recent_transactions
GROUP BY block_number, block_timestamp
```

### Recent Transactions with the Highest Fee

Gets the top 10 transactions that paid the highest fee within the past 30 minutes.

**Typical query time**: 1 second

```sql
SELECT fee / 1e8 as fee_in_btc, * 
FROM btc.recent_transactions 
ORDER BY fee DESC 
LIMIT 10
```
