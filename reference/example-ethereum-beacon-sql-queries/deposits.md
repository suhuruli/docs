# Deposits

### Weekly Deposits Count

Number of new validator deposits by week

**Typical query time**: <15 seconds

```sql
SELECT
  DATE_TRUNC('week', TO_TIMESTAMP(block_timestamp)) AS deposit_week,
  COUNT(*) AS num_new_validator_deposits
FROM
  eth.beacon.deposits
GROUP BY
  deposit_week
ORDER BY
  deposit_week DESC
```
