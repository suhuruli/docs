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

