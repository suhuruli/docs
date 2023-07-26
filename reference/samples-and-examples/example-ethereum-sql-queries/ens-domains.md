# ENS Domains

### Retrieve an Ethereum address

Get the Ethereum address of a domain or subdomain, or perform a reverse look-up.

#### Look up a domain

**Typical query time**: <1 second.

```sql
--- *.eth domain look-up:
SELECT * FROM ens.domains WHERE name='spiceai.eth'
```

#### Look up a subdomain

**Typical query time**: <1 second.

```sql
SELECT * FROM ens.domains WHERE name='ccc.earth.eth'
```

#### Reverse lookup a domain from eth\_address

**Typical query time**: <1 second.

```sql
--- reverse look-up:
SELECT * FROM ens.domains WHERE eth_address='0x425ec049c2a4722edfd770ab7bc4f9ca8b7bd815'
```

