# BLS To Execution Changes

### Counting Validators per Execution Address Sorted by Popularity

This query retrieves the number of validators associated with each execution address by counting the recent BLS (Boneh-Lynn-Shacham) signature to execution address changes in the Ethereum beacon chain. The results are grouped by the execution address and sorted in descending order based on the validator count.

**Typical query time**: <5 seconds

```sql
SELECT to_execution_address, COUNT(1) as num_validators
FROM eth.beacon.recent_bls_to_execution_changes
GROUP BY to_execution_address
ORDER BY COUNT(1) DESC
```
