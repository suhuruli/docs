---
description: Ethereum Name Service tables
---

# ENS Tables

{% hint style="warning" %}
ENS support is in beta
{% endhint %}

#### **Ethereum Name Service (ENS) tables**

| Table Name    | Description                         |
| ------------- | ----------------------------------- |
| `ens.domains` | A mapping of ENS names to addresses |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE ens.domains;
```
