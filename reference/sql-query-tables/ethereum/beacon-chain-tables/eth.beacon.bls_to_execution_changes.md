---
description: >-
  SQL table schema for eth.beacon.bls_to_execution_changes and
  eth.beacon.recent_bls_to_execution_changes
---

# eth.beacon.bls\_to\_execution\_changes

Ethereum Beacon requests to change old BLS withdrawal credentials to the new withdrawal credentials in execution address format.

| Column Name            | Data Type         |
| ---------------------- | ----------------- |
| `block_slot`           | DOUBLE            |
| `block_root`           | CHARACTER VARYING |
| `block_timestamp`      | BIGINT            |
| `validator_index`      | DOUBLE            |
| `from_bls_pubkey`      | CHARACTER VARYING |
| `to_execution_address` | CHARACTER VARYING |
| `signature`            | CHARACTER VARYING |
