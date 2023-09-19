# Withdrawals

### Total ETH withdrawn from the Beacon Chain

**Typical query time**: <5 seconds

```sql
SELECT sum(amount / 1e9) AS withdrawn_eth 
FROM eth.beacon.withdrawals
```

### Latest 10 Withdrawals

**Typical query time**: <5 seconds

```sql
SELECT block_slot, amount / 1e9 as withdrawn_eth, TO_TIMESTAMP(block_timestamp) as block_timestamp, address, withdrawal_index
FROM eth.beacon.recent_withdrawals
ORDER BY withdrawal_index DESC
LIMIT 10
```

### Most ETH Withdrawn to a single address, within the last 30 minutes

**Typical query time**: <5 seconds

```sql
SELECT SUM(amount / 1e9) as withdrawn_eth, address
FROM eth.beacon.recent_withdrawals
GROUP BY address
ORDER BY SUM(amount / 1e9) DESC
LIMIT 100
```
