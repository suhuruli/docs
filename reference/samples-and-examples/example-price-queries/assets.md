---
description: Example queries that use the SpiceAI Assets dataset
---

## Assets

### Find ID for supported Ethereum token

Finds the asset_id to use in SpiceAI for an ethereum token.

**Typical query time**: 30 millisecond

```sql
SELECT asset_id
FROM spiceai.assets
WHERE eth_address='0xaa379c2aa72529d5ec0da8a41e2f41ed7fe4b48c' -- `polygon_address` also supported
```

Or find all ethereum tokens

**Typical query time**: 40 millisecond

```sql
SELECT asset_id
FROM spiceai.assets
WHERE eth_address IS NOT NULL
```