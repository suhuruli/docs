---
description: Spice ML Models YAML manifest Specification v0.2 (beta)
---

# Models YAML Specification

Spice ML Models are defined in YAML. To create a Model, add a manifest YAML file to the `/models` path of a connected [GitHub repository](../../portal/apps/connect-github-repository.md).

### **YAML Schema Reference**

### **`name`**

The name of the model. Only alpha characters and underscores are supported with no spaces.

### **`description`** \[optional]

An optional description for the model.

### **`family`** \[optional]

The model family.

### **`type`** \[optional]

The model type.

### **`metadata`**

A key-value bag of metadata/parameters for the model.

### **`handler`**

The code file that contains the entry points for training and inferencing.

E.g. `gas_fees.py`

### `training`

**Optional**. Defines training for the model.

**Example**

```yaml
training:
  entry_point: gas_fees.train
  sql: 'WITH counts AS (    SELECT block_number, count(1) as "count" FROM eth.recent_transactions GROUP BY block_number  )  SELECT number as "ts", CAST(b.base_fee_per_gas / 1000000000.0 AS DOUBLE) as "y", CAST(c."count" AS DOUBLE) as "y2"  FROM eth.recent_blocks b  INNER JOIN counts c ON b.number = c.block_number  WHERE b.base_fee_per_gas IS NOT NULL ORDER BY block_number DESC LIMIT 500'
  loggers:
    - tensorboard
```

**`entry_point`**

The entry point (function) for training.

E.g. `gas_fees.train`

**`sql`**

The Spice.ai SQL query for fetching training data.

E.g. `WITH counts AS (    SELECT block_number, count(1) as "count" FROM eth.recent_transactions GROUP BY block_number  )  SELECT number as "ts", CAST(b.base_fee_per_gas / 1000000000.0 AS DOUBLE) as "y", CAST(c."count" AS DOUBLE) as "y2"  FROM eth.recent_blocks b  INNER JOIN counts c ON b.number = c.block_number  WHERE b.base_fee_per_gas IS NOT NULL ORDER BY block_number DESC LIMIT 500`

#### `loggers`

A list of loggers to enable for each training run.

Supported loggers and their values are:

| Logger                                                 | Value         |
| ------------------------------------------------------ | ------------- |
| [TensorBoard](https://www.tensorflow.org/tensorboard/) | `tensorboard` |

_**Example**_

```yaml
training:
  loggers:
    - tensorboard
```

### `inference`

**Optional**. Defines inferencing for the model.

**Example**

```yaml
inferencing:
  entry_point: gas_fees.train
  sql: 'WITH counts AS (    SELECT block_number, count(1) as "count" FROM eth.recent_transactions GROUP BY block_number  )  SELECT number as "ts", CAST(b.base_fee_per_gas / 1000000000.0 AS DOUBLE) as "y", CAST(c."count" AS DOUBLE) as "y2"  FROM eth.recent_blocks b  INNER JOIN counts c ON b.number = c.block_number  WHERE b.base_fee_per_gas IS NOT NULL ORDER BY block_number DESC LIMIT 500'
  lookback_size: 30
  forecast_size: 1
```

**`entry_point`**

The entry point (function) for inferencing.

E.g. `gas_fees.infer`

**`sql`**

The Spice.ai SQL query for fetching inferencing data.

E.g. `SELECT number as "ts", CAST(base_fee_per_gas / 1000000000.0 AS DOUBLE) as "y", CAST(transaction_count AS DOUBLE) as "y2" from eth.recent_blocks WHERE base_fee_per_gas IS NOT NULL ORDER BY ts DESC LIMIT 35`

**`lookback_size`**

The lookback size/window.

**`forecast_size`**

The forecast size/window.

### Example definition

```yaml
# /models/gas_fees/model.yml
name: v0.1
family: gas_fees
description: A Ethereum gas fee forecasting model.
type: gasfees_v1
handler: gas_fees.py
training
  entry_point: gas_fees.train
  sql: 'WITH counts AS (    SELECT block_number, count(1) as "count" FROM eth.recent_transactions GROUP BY block_number  )  SELECT number as "ts", CAST(b.base_fee_per_gas / 1000000000.0 AS DOUBLE) as "y", CAST(c."count" AS DOUBLE) as "y2"  FROM eth.recent_blocks b  INNER JOIN counts c ON b.number = c.block_number  WHERE b.base_fee_per_gas IS NOT NULL ORDER BY block_number DESC LIMIT 500'
inference
  entry_point: gas_fees.infer
  sql: 'SELECT number as "ts", CAST(base_fee_per_gas / 1000000000.0 AS DOUBLE) as "y", CAST(transaction_count AS DOUBLE) as "y2" from eth.recent_blocks WHERE base_fee_per_gas IS NOT NULL ORDER BY ts DESC LIMIT 35'
  lookback_size: 30
  forecast_size: 1
metadata:
  firecache: true
  covariate: true
```
