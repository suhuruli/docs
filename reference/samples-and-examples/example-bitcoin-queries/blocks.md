# Blocks

### Monthly Block Count

Gets the number of blocks produced each month.

**Typical query time**: 1-2 second

```sql
SELECT 
  DATE_TRUNC('month', TO_TIMESTAMP("timestamp")) AS "month", 
  COUNT(*) AS block_count
FROM btc.blocks
GROUP BY "month" ORDER BY "month" DESC
```
