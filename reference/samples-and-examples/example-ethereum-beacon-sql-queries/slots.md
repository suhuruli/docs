# Slots

### Beacon Slots from the last 30 minutes

**Typical query time**: <1-3 seconds

```sql
SELECT
  block_slot, block_epoch, TO_TIMESTAMP(block_timestamp) as block_timestamp, execution_payload_block_number, skipped 
FROM
  eth.beacon.recent_slots 
ORDER BY block_slot DESC
LIMIT 10
```

### Skipped Slots

Percentage of empty slots (slots without processed blocks)

**Typical query time**: <10 seconds

```sql
SELECT
  COUNT(*) * 100.0 / (SELECT COUNT(*) FROM eth.beacon.slots) AS empty_slot_percentage
FROM
  eth.beacon.slots
WHERE
  skipped = true
```

### Most Frequent Proposers

Top 10 most frequent block proposers

**Typical query time**: <15 seconds

```sql
SELECT
  proposer_index,
  COUNT(*) AS num_proposed_blocks
FROM
  eth.beacon.slots
WHERE
  skipped = false
GROUP BY
  proposer_index
ORDER BY
  num_proposed_blocks DESC
LIMIT 10
```

