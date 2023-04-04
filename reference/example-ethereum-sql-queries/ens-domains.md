# ENS Domains

### Retrieve an Ethereum address

Get the Ethereum address of a domain or subdomain, or perform a reverse look-up.

**Typical query time**: <1 second.

```sql
--- *.eth domains and subdomains look-up:
SELECT *, TO_TIMESTAMP(expires) AS datetime FROM ens.domains WHERE name='covolan.eth'
SELECT *, TO_TIMESTAMP(expires) AS datetime FROM ens.domains WHERE name='ccc.earth.eth'

--- revserse look-up:
SELECT *, TO_TIMESTAMP(expires) AS datetime FROM ens.domains WHERE eth_address='0x73690db4433c90111bafd0e20e4e43b54696b050'
```

