# flow.transactions

| Column Name                    | Data Type                |
| ------------------------------ | ------------------------ |
| `id`                           | CHARACTER VARYING        |
| `block_id`                     | CHARACTER VARYING        |
| `block_height`                 | BIGINT                   |
| `block_timestamp`              | BIGINT                   |
| `script`                       | BYTEA                    |
| `arguments`                    | LIST\<CHARACTER VARYING> |
| `reference_block_id`           | CHARACTER VARYING        |
| `gas_limit`                    | BIGINT                   |
| `proposal_key_address`         | CHARACTER VARYING        |
| `proposal_key_index`           | INTEGER                  |
| `proposal_key_sequence_number` | BIGINT                   |
| `payer`                        | CHARACTER VARYING        |
| `authorizers`                  | LIST\<CHARACTER VARYING> |

Indexed columns:

* `id`
* `block_height`
* `block_id`
