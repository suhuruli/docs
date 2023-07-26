# flow.transactions

| Column Name                    | Data Type                | Description                                                                                 |
| ------------------------------ | ------------------------ | ------------------------------------------------------------------------------------------- |
| `id`                           | CHARACTER VARYING        | The id of this transaction.                                                                 |
| `block_id`                     | CHARACTER VARYING        | The id of the block in which this transaction occurred.                                     |
| `block_height`                 | BIGINT                   | The height of the block in which this transaction occurred.                                 |
| `block_timestamp`              | BIGINT                   | The time (in Unix seconds) of the block in which this transaction occurred, eg. 1687402358. |
| `script`                       | BYTEA                    | Base64-encoded content of a Cadence script.                                                 |
| `arguments`                    | LIST\<CHARACTER VARYING> | List of arguments passed to the script.                                                     |
| `reference_block_id`           | CHARACTER VARYING        | The id of a reference block for this transaction.                                           |
| `gas_limit`                    | BIGINT                   | The limit to the amount of computation this transaction was allowed to perform, eg. 9999.   |
| `proposal_key_address`         | CHARACTER VARYING        | The address of the account that proposed this transaction, eg. `63001addadf8fffa`.          |
| `proposal_key_index`           | INTEGER                  | The index of the key used by the proposer to sign the transaction, eg. 1675.                |
| `proposal_key_sequence_number` | BIGINT                   | The sequence number of the proposer's account at the time of proposal, eg, 25229.           |
| `payer`                        | CHARACTER VARYING        | The address of an account that funded this transaction, eg. `1e3c78c6d580273b`.             |
| `authorizers`                  | LIST\<CHARACTER VARYING> | A list of addresses that have authorized this transaction.                                  |

Indexed columns:

* `id`
* `block_height`
* `block_id`
