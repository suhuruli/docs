# Gas & Fees

### High gas usage&#x20;

**Typical query time**: \~60 seconds

```sql
SELECT 
  DATE_TRUNC('day', TO_TIMESTAMP("timestamp")) AS day,
  SUM(gas_used) AS total_gas
FROM eth.blocks
GROUP BY day
ORDER BY total_gas DESC
LIMIT 10;
```
