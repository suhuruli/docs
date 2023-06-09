---
description: Goerli Beacon Chain tables available to query via SQL
---

# Beacon Chain Tables

#### Goerli Beacon tables available to query

| Table Name                                                                                      | Description                                                                                                                                                                              |
| ----------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`goerli.beacon.validators`](goerli.beacon.validators.md)                                       | Latest validators, with their status and current balance                                                                                                                                 |
| [`goerli.beacon.slots`](goerli.beacon.slots.md)                                                 | This table contains data about each slot in the Beacon Chain.                                                                                                                            |
| [`goerli.beacon.recent_slots`](goerli.beacon.slots.md)                                          | Slots from the past 30 minutes.                                                                                                                                                          |
| [`goerli.beacon.attestations`](goerli.beacon.attestations.md)                                   | This table stores data about attestations made by validators on the Beacon Chain.                                                                                                        |
| [`goerli.beacon.recent_attestations`](goerli.beacon.attestations.md)                            | Attestations from the past 30 minutes.                                                                                                                                                   |
| [`goerli.beacon.deposits`](goerli.beacon.deposits.md)                                           | This table contains data about validator deposits made on the Beacon Chain.                                                                                                              |
| [`goerli.beacon.recent_deposits`](goerli.beacon.deposits.md)                                    | Deposits from the past 30 minutes.                                                                                                                                                       |
| [`goerli.beacon.voluntary_exits`](goerli.beacon.voluntary\_exits.md)                            | This table stores data about voluntary exits of validators from the Beacon Chain.                                                                                                        |
| [`goerli.beacon.recent_voluntary_exits`](goerli.beacon.voluntary\_exits.md)                     | Voluntary exits from the past 30 minutes.                                                                                                                                                |
| [`goerli.beacon.attester_slashings`](goerli.beacon.attester\_slashings.md)                      | This table contains information about attester slashings on the Beacon Chain. Occurs when a validator has made conflicting attestations                                                  |
| [`goerli.beacon.recent_attester_slashings`](goerli.beacon.attester\_slashings.md)               | Attester slashings from the past 30 minutes                                                                                                                                              |
| [`goerli.beacon.proposer_slashings`](goerli.beacon.proposer\_slashings.md)                      | This table stores data about proposer slashings on the Beacon Chain. Proposer slashings occur when a validator has been found to have proposed two conflicting blocks for the same slot. |
| [`goerli.beacon.recent_proposer_slashings`](goerli.beacon.proposer\_slashings.md)               | Proposer slashings from the past 30 minutes                                                                                                                                              |
| [`goerli.beacon.bls_to_execution_changes`](goerli.beacon.bls\_to\_execution\_changes.md)        | Requests to change old BLS withdrawal credentials to the new withdrawal credentials in execution address format                                                                          |
| [`goerli.beacon.recent_bls_to_execution_changes`](goerli.beacon.bls\_to\_execution\_changes.md) | Requests from the past 30 minutes                                                                                                                                                        |
| [`goerli.beacon.withdrawals`](goerli.beacon.withdrawals.md)                                     | Withdrawals of ETH from the beacon chain to the Goerli testnet chain                                                                                                                     |
| [`goerli.beacon.recent_withdrawals`](goerli.beacon.withdrawals.md)                              | Withdrawals from the past 30 minutes                                                                                                                                                     |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN goerli.beacon
```
