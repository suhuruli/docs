# Voluntary Exits

### Voluntary Exits Count

Number of validators who have signaled intent to exit

**Typical query time**: <10 seconds

```sql
SELECT
  COUNT(DISTINCT validator_index) AS num_unique_exited_validators
FROM
  eth.beacon.voluntary_exits
```
