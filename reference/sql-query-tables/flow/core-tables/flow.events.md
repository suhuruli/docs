# flow.events

| Column Name       | Data Type                |
| ----------------- | ------------------------ |
| `block_id`        | CHARACTER VARYING        |
| `block_height`    | BIGINT                   |
| `block_timestamp` | BIGINT                   |
| `type`            | CHARACTER VARYING        |
| `transaction_id`  | CHARACTER VARYING        |
| `index`           | INTEGER                  |
| `fields`          | LIST\<CHARACTER VARYING> |
| `payload`         | BYTEA                    |

Indexed columns:

* `transaction_id`
* `block_id`
* `block_height`
