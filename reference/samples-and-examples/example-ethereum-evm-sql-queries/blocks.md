# Blocks

### Orphaned Ethereum Blocks

**Typical query time**: \~60 seconds

```sql
SELECT 
  b1.number, 
  b1.hash, 
  b1.parent_hash
FROM eth.blocks AS b1
LEFT JOIN eth.blocks AS b2 ON b1.parent_hash = b2.hash
WHERE b2.hash IS NULL;
```

