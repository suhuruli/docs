---
description: Ethereum Beacon tables available to query via SQL
---

# Beacon Chain Tables

#### Ethereum Beacon tables available to query

| Table Name                                                                                | Description                                                                                                                                                                              |
| ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`eth.beacon.validators`](eth.beacon.validators.md)                                       | Latest validators, with their status and current balance                                                                                                                                 |
| [`eth.beacon.slots`](eth.beacon.slots.md)                                                 | This table contains data about each slot in the Beacon Chain.                                                                                                                            |
| [`eth.beacon.recent_slots`](eth.beacon.slots.md)                                          | Slots from the past 30 minutes.                                                                                                                                                          |
| [`eth.beacon.attestations`](eth.beacon.attestations.md)                                   | This table stores data about attestations made by validators on the Beacon Chain.                                                                                                        |
| [`eth.beacon.recent_attestations`](eth.beacon.attestations.md)                            | Attestations from the past 30 minutes.                                                                                                                                                   |
| [`eth.beacon.deposits`](eth.beacon.deposits.md)                                           | This table contains data about validator deposits made on the Beacon Chain.                                                                                                              |
| [`eth.beacon.recent_deposits`](eth.beacon.deposits.md)                                    | Deposits from the past 30 minutes.                                                                                                                                                       |
| [`eth.beacon.voluntary_exits`](eth.beacon.voluntary\_exits.md)                            | This table stores data about voluntary exits of validators from the Beacon Chain.                                                                                                        |
| [`eth.beacon.recent_voluntary_exits`](eth.beacon.voluntary\_exits.md)                     | Voluntary exits from the past 30 minutes.                                                                                                                                                |
| [`eth.beacon.attester_slashings`](eth.beacon.attester\_slashings.md)                      | This table contains information about attester slashings on the Beacon Chain. Occurs when a validator has made conflicting attestations                                                  |
| [`eth.beacon.recent_attester_slashings`](eth.beacon.attester\_slashings.md)               | Attester slashings from the past 30 minutes                                                                                                                                              |
| [`eth.beacon.proposer_slashings`](eth.beacon.proposer\_slashings.md)                      | This table stores data about proposer slashings on the Beacon Chain. Proposer slashings occur when a validator has been found to have proposed two conflicting blocks for the same slot. |
| [`eth.beacon.recent_proposer_slashings`](eth.beacon.proposer\_slashings.md)               | Proposer slashings from the past 30 minutes                                                                                                                                              |
| [`eth.beacon.bls_to_execution_changes`](eth.beacon.bls\_to\_execution\_changes.md)        | Requests to change old BLS withdrawal credentials to the new withdrawal credentials in execution address format                                                                          |
| [`eth.beacon.recent_bls_to_execution_changes`](eth.beacon.bls\_to\_execution\_changes.md) | Requests from the past 30 minutes                                                                                                                                                        |
| [`eth.beacon.withdrawals`](eth.beacon.withdrawals.md)                                     | Withdrawals of ETH from the beacon chain to the main Ethereum chain                                                                                                                      |
| [`eth.beacon.recent_withdrawals`](eth.beacon.withdrawals.md)                              | Withdrawals from the past 30 minutes                                                                                                                                                     |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN eth.beacon
```
