# flow.events

| Column Name       | Data Type                | Description                                                                                                               |
| ----------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| `block_id`        | CHARACTER VARYING        | The id of the block in which this event occurred, eg. `d6fa361d7619088b3025a34f5d7a636ffe00f547ae96d178d86842856ad88d3d`. |
| `block_height`    | BIGINT                   | The height of the block in which this transfer occurred, eg. 55145419.                                                    |
| `block_timestamp` | BIGINT                   | The time (in Unix seconds) of the block in which this event occurred, eg. 1687402358.                                     |
| `type`            | CHARACTER VARYING        | The type of this event, eg. `A.e4cf4bdc1751c65d.AllDay.Withdraw`                                                          |
| `transaction_id`  | CHARACTER VARYING        | The Flow transaction that enacted this event, eg. `b1dc50b4200e4716f93dc761f12270e077b8e85ed9f5683c87bdb2f0c4dbc189`.     |
| `index`           | INTEGER                  | The index of the event within the block, eg. 5.                                                                           |
| `fields`          | LIST\<CHARACTER VARYING> | A list of fields in this event, eg. `[0.95000000, nil]`                                                                   |
| `payload`         | BYTEA                    | The data payload associated with this event.                                                                              |

Indexed columns:

* `transaction_id`
* `block_id`
* `block_height`
