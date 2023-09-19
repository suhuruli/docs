---
description: SQL table schema for ens.domains
---

# ens.domains

Ethereum Name Service (ENS) tables mapping of ENS names to addresses.

| Column Name   | Data Type         | Description                                                                               |
| ------------- | ----------------- | ----------------------------------------------------------------------------------------- |
| `name`        | CHARACTER VARYING | The public (typically human-readable) name registration that points to the `eth_address`. |
| `eth_address` | CHARACTER VARYING | The on-chain address that the `name` points to.                                           |
| `owner`       | CHARACTER VARYING | The address of the owner of this registration.                                            |
| `expires`     | DECIMAL           | The expiry timestamp for this registration.                                               |

