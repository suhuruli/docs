---
description: Ethereum Name Service tables
---

# ENS Tables

#### **Ethereum Name Service (ENS) tables**

| Table Name    | Description                         |
| ------------- | ----------------------------------- |
| `ens.domains` | A mapping of ENS names to addresses |

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

<pre class="language-sql"><code class="lang-sql"><strong>SELECT *, TO_TIMESTAMP(expires) AS datetime FROM ens.domains WHERE name='covolan.eth'
</strong>SELECT *, TO_TIMESTAMP(expires) AS datetime FROM ens.domains WHERE name='ccc.earth.eth'
</code></pre>

Or to infer the domain name of an address (reverse look-up):

```sql
SELECT *, TO_TIMESTAMP(expires) AS datetime FROM ens.domains WHERE eth_address='0x73690db4433c90111bafd0e20e4e43b54696b050'
```

Expiration dates in the `expires` column are given as Unix timestamps. They can be `null` for entities such as subdomains, which do not necessarily have expiry dates. We currently do not track expiration dates of [NameWrapper subdomains](https://github.com/ensdomains/ens-contracts/tree/master/contracts/wrapper).

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name    | Indexed Columns        |
| ------------- | ---------------------- |
| `ens.domains` | `name`, `eth_address`  |
