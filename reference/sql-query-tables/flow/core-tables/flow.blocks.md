# flow.blocks

Flow block headers

| Column Name | Data Type         |
| ----------- | ----------------- |
| `id`        | CHARACTER VARYING |
| `parent_id` | CHARACTER VARYING |
| `height`    | BIGINT            |
| `timestamp` | BIGINT            |
| `status`    | INTEGER           |

Indexed columns:

* `id`
* `height`
* `timestamp`
