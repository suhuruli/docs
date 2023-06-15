---
description: SQL table schema for ens.domains
---

# ens.domains

Ethereum Name Service (ENS) tables mapping of ENS names to addresses.

| Column Name   | Data Type         |
| ------------- | ----------------- |
| `name`        | CHARACTER VARYING |
| `eth_address` | CHARACTER VARYING |
| `owner`       | CHARACTER VARYING |
| `expires`     | DECIMAL           |
