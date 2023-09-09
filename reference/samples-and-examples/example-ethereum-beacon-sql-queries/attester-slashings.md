# Attester Slashings

### Weekly Attester Slashings Count

Number of attester slashings per week

**Typical query time**: <5 seconds

```sql
SELECT
  DATE_TRUNC('week', TO_TIMESTAMP(block_timestamp)) AS slashing_week,
  COUNT(*) AS num_attester_slashings
FROM
  eth.beacon.attester_slashings
GROUP BY
  slashing_week
ORDER BY
  slashing_week DESC
```
