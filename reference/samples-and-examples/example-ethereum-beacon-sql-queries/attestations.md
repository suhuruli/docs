# Attestations

### Attestations statistics

Average number of attestations per slot

**Typical query time**: <15 seconds

```sql
SELECT
  AVG(num_attestations) AS average_attestations_per_slot
FROM (
  SELECT
    block_slot,
    COUNT(*) AS num_attestations
  FROM
    eth.beacon.attestations
  GROUP BY
    block_slot
) AS attestations_per_slot
```
