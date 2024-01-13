---
description: Holesky Beacon Chain tables available to query via SQL
---

# Beacon Chain Tables

#### Holesky Beacon tables available to query

| Table Name                                                                                        | Description                                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`holesky.beacon.validators`](holesky.beacon.validators.md)                                       | Latest validators, with their status and current balance                                                                                                                                 |
| [`holesky.beacon.slots`](holesky.beacon.slots.md)                                                 | This table contains data about each slot in the Beacon Chain.                                                                                                                            |
| [`holesky.beacon.recent_slots`](holesky.beacon.slots.md)                                          | Slots from the past 30 minutes.                                                                                                                                                          |
| [`holesky.beacon.attestations`](holesky.beacon.attestations.md)                                   | This table stores data about attestations made by validators on the Beacon Chain.                                                                                                        |
| [`holesky.beacon.recent_attestations`](holesky.beacon.attestations.md)                            | Attestations from the past 30 minutes.                                                                                                                                                   |
| [`holesky.beacon.deposits`](holesky.beacon.deposits.md)                                           | This table contains data about validator deposits made on the Beacon Chain.                                                                                                              |
| [`holesky.beacon.recent_deposits`](holesky.beacon.deposits.md)                                    | Deposits from the past 30 minutes.                                                                                                                                                       |
| [`holesky.beacon.voluntary_exits`](holesky.beacon.voluntary\_exits.md)                            | This table stores data about voluntary exits of validators from the Beacon Chain.                                                                                                        |
| [`holesky.beacon.recent_voluntary_exits`](holesky.beacon.voluntary\_exits.md)                     | Voluntary exits from the past 30 minutes.                                                                                                                                                |
| [`holesky.beacon.attester_slashings`](holesky.beacon.attester\_slashings.md)                      | This table contains information about attester slashings on the Beacon Chain. Occurs when a validator has made conflicting attestations                                                  |
| [`holesky.beacon.recent_attester_slashings`](holesky.beacon.attester\_slashings.md)               | Attester slashings from the past 30 minutes                                                                                                                                              |
| [`holesky.beacon.proposer_slashings`](holesky.beacon.proposer\_slashings.md)                      | This table stores data about proposer slashings on the Beacon Chain. Proposer slashings occur when a validator has been found to have proposed two conflicting blocks for the same slot. |
| [`holesky.beacon.recent_proposer_slashings`](holesky.beacon.proposer\_slashings.md)               | Proposer slashings from the past 30 minutes                                                                                                                                              |
| [`holesky.beacon.bls_to_execution_changes`](holesky.beacon.bls\_to\_execution\_changes.md)        | Requests to change old BLS withdrawal credentials to the new withdrawal credentials in execution address format                                                                          |
| [`holesky.beacon.recent_bls_to_execution_changes`](holesky.beacon.bls\_to\_execution\_changes.md) | Requests from the past 30 minutes                                                                                                                                                        |
| [`holesky.beacon.withdrawals`](holesky.beacon.withdrawals.md)                                     | Withdrawals of ETH from the beacon chain to the Goerli testnet chain                                                                                                                     |
| [`holesky.beacon.recent_withdrawals`](holesky.beacon.withdrawals.md)                              | Withdrawals from the past 30 minutes                                                                                                                                                     |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN holesky.beacon
```
