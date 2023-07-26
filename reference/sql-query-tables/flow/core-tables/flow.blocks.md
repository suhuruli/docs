# flow.blocks

Flow block headers

| Column Name | Data Type         | Description                                                                                   |
| ----------- | ----------------- | --------------------------------------------------------------------------------------------- |
| `id`        | CHARACTER VARYING | The id of this block, eg. `d6fa361d7619088b3025a34f5d7a636ffe00f547ae96d178d86842856ad88d3d`. |
| `parent_id` | CHARACTER VARYING | The id of the parent block of this block.                                                     |
| `height`    | BIGINT            | The height of this block, eg. 55145419.                                                       |
| `timestamp` | BIGINT            | The time (in Unix seconds) when this block was created, eg. 1687402358.                       |
| `status`    | INTEGER           | The status of this block, eg. 0.                                                              |

Indexed columns:

* `id`
* `height`
* `timestamp`
