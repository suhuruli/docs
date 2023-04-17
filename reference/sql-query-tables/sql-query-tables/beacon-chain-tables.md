---
description: Ethereum Beacon tables available to query via SQL
---

# Beacon Chain Tables

#### Ethereum Beacon tables available to query

| Table Name                                   | Description                                                                                                                                                                              |
| -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `eth.validators`                             | Latest validators, with their status and current balance                                                                                                                                 |
| `eth.beacon.slots`                           | This table contains data about each slot in the Beacon Chain.                                                                                                                            |
| `eth.beacon.recent_slots`                    | Slots from the past 30 minutes.                                                                                                                                                          |
| `eth.beacon.attestations`                    | This table stores data about attestations made by validators on the Beacon Chain.                                                                                                        |
| `eth.beacon.recent_attestations`             | Attestations from the past 30 minutes.                                                                                                                                                   |
| `eth.beacon.deposits`                        | This table contains data about validator deposits made on the Beacon Chain.                                                                                                              |
| `eth.beacon.recent_deposits`                 | Deposits from the past 30 minutes.                                                                                                                                                       |
| `eth.beacon.voluntary_exits`                 | This table stores data about voluntary exits of validators from the Beacon Chain.                                                                                                        |
| `eth.beacon.recent_voluntary_exits`          | Voluntary exits from the past 30 minutes.                                                                                                                                                |
| `eth.beacon.attester_slashings`              | This table contains information about attester slashings on the Beacon Chain. Occurs when a validator has made conflicting attestations                                                  |
| `eth.beacon.recent_attester_slashings`       | Attester slashings from the past 30 minutes                                                                                                                                              |
| `eth.beacon.proposer_slashings`              | This table stores data about proposer slashings on the Beacon Chain. Proposer slashings occur when a validator has been found to have proposed two conflicting blocks for the same slot. |
| `eth.beacon.recent_proposer_slashings`       | Proposer slashings from the past 30 minutes                                                                                                                                              |
| `eth.beacon.bls_to_execution_changes`        | Requests to change old BLS withdrawal credentials to the new withdrawal credentials in execution address format                                                                          |
| `eth.beacon.recent_bls_to_execution_changes` | Requests from the past 30 minutes                                                                                                                                                        |
| `eth.beacon.withdrawals`                     | Withdrawals of ETH from the beacon chain to the main Ethereum chain                                                                                                                      |
| `eth.beacon.recent_withdrawals`              | Withdrawals from the past 30 minutes                                                                                                                                                     |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN eth.beacon
```
