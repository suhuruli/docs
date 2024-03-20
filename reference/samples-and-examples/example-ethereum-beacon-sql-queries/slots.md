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

### Beacon Slots with Blob data&#x20;

Beacon Slots with the highest number of blobs in the last 4 hours

**Typical query time**: <5 seconds

```sql
SELECT 
  block_slot, 
  ARRAY_SIZE(blob_kzg_commitments) as num_blobs,
  blob_gas_used
FROM eth.beacon.slots 
WHERE blob_gas_used > 0 and block_timestamp > UNIX_TIMESTAMP() - 4 * 60 * 60
ORDER BY num_blobs DESC
```
