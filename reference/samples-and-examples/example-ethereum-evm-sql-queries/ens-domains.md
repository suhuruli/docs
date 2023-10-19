# ENS Domains

### Ethereum address of ENS Domain

**Typical query time**: <1 seconds

```sql
SELECT eth_address
FROM ens.domains
WHERE name='spiceai.eth'
LIMIT 1
```

### Expired ENS Domains

**Typical query time**: 3-4 seconds

```sql
SELECT 
    name, eth_address
FROM 
    ens.domains
WHERE
    EXTRACT(EPOCH FROM NOW()) > expires
```
