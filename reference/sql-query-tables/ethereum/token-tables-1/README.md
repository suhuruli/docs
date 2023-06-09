---
description: Ethereum Name Service (ENS) tables available to query via SQL
---

# ENS Tables

#### **Ethereum Name Service (ENS) tables**

| Table Name                      | Description                         |
| ------------------------------- | ----------------------------------- |
| [`ens.domains`](ens.domains.md) | A mapping of ENS names to addresses |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE ens.domains;
```

User can query this table by ENS domain name to retrieve the latest `owner` and `eth_address` information. Supported names are:

* Top Level Domains (.eth)
* Subdomains
  * dcl.eth
  * loopring.eth
  * argent.xyz
  * earth.eth
  * auth.eth

This table can be used, for example, to retrieve the Ethereum address associated with a  `*.eth` domain or subdomain:

```sql
SELECT * FROM ens.domains WHERE name='spiceai.eth'
SELECT * FROM ens.domains WHERE name='ccc.earth.eth'
```

Or to infer the domain name of an address (reverse look-up):

```sql
SELECT * FROM ens.domains WHERE eth_address='0x425ec049c2a4722edfd770ab7bc4f9ca8b7bd815'
```

Expiration dates in the `expires` column are given as Unix timestamps. They can be `null` for entities such as subdomains, which do not necessarily have expiry dates. We currently do not track expiration dates of [NameWrapper subdomains](https://github.com/ensdomains/ens-contracts/tree/master/contracts/wrapper).

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name    | Indexed Columns        |
| ------------- | ---------------------- |
| `ens.domains` | `name`, `eth_address`  |
