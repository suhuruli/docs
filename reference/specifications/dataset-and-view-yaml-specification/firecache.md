---
description: Dataset firecache definition
---

# Firecache

### Schema Properties

**`enabled`**

Set to `true` to enable this dataset for Firecache.

**`trigger`**

The trigger event type for when to update the Firecache. Valid values are `block_number` `block_slot` .

**`time_column`**

The dataset column that represents time. For example `timestamp` for the [eth.blocks](../../sql-query-tables/ethereum/core-tables/eth.blocks.md) table or `block_timestamp` for the [eth.transactions](../../sql-query-tables/ethereum/core-tables/eth.transactions.md) table.

### Example definition

```yaml
firecache:
  enabled: true
  trigger: block_number
  time_column: block_timestamp
```
