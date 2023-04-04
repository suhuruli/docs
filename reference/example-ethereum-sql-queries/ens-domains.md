# ENS Domains

### Retrieve an Ethereum address

Get the Ethereum address of a domain or subdomain, or perform a reverse look-up.

**Typical query time**: <1 second.

```sql
--- *.eth domains and subdomains look-up:
SELECT * FROM ens.domains WHERE name='spiceai.eth'
SELECT * FROM ens.domains WHERE name='ccc.earth.eth'

--- revserse look-up:
SELECT * FROM ens.domains WHERE eth_address='0x425ec049c2a4722edfd770ab7bc4f9ca8b7bd815'
```

