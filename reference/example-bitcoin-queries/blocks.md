# Blocks

### Get Latest Block Number

Gets the number of the latest block in the chain.

**Typical query time**: < 1 second.

```sql
SELECT max(number) as latest_block_number
FROM btc.recent_blocks
```

### Last 5000 Blocks

Gets basic information for the last 5000 blocks in the chain

{% hint style="info" %}
To get access to more than 500 results, use the [Apache Arrow Flight API](../../api/sql-query-api/apache-arrow-flight-api.md).
{% endhint %}

**Typical query time**: 2 seconds

```sql
SELECT number, "timestamp", hash, transaction_count
FROM btc.blocks
ORDER BY number DESC
LIMIT 5000
```

### Blocks with the Highest Number of Transactions

Gets the list of blocks with the highest number of transactions that were included in that block, sorted in descending order.

**Typical query time**: 3 seconds

```sql
SELECT number, "timestamp", transaction_count
FROM btc.blocks 
ORDER BY transaction_count DESC 
LIMIT 500
```
