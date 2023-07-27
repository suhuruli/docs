---
description: >-
  SQL table schema for eth.beacon.bls_to_execution_changes and
  eth.beacon.recent_bls_to_execution_changes
---

# eth.beacon.bls\_to\_execution\_changes

Ethereum Beacon requests to change old BLS withdrawal credentials to the new withdrawal credentials in execution address format.

| Column Name            | Data Type         | Description                                                                |
| ---------------------- | ----------------- | -------------------------------------------------------------------------- |
| `block_slot`           | DOUBLE            | The slot in the beacon chain in which the change was undertaken.           |
| `block_root`           | CHARACTER VARYING | The root hash of the beacon chain block containing the change.             |
| `block_timestamp`      | BIGINT            | The timestamp of the  beacon chain block containing the change.            |
| `validator_index`      | DOUBLE            | The index for the validator who made the change request.                   |
| `from_bls_pubkey`      | CHARACTER VARYING | BLS public key of the validator.                                           |
| `to_execution_address` | CHARACTER VARYING | The execution address set as the withdrawal credentials for the validator. |
| `signature`            | CHARACTER VARYING | Signature of change request                                                |
