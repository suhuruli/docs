# Dataset & View YAML Specification

Spice Datasets and Views are defined in YAML. To create a Dataset or View, add a dataset YAML to the `.spice/datasets` path of the connected [GitHub repository](../../../portal/apps/connect-github-repository.md).

### **YAML Schema Reference**

**`name`**

The name of the dataset. Only alpha characters and underscores are supported with no spaces.

**`description`** \[optional]

An optional description for the dataset.

**`type`**

The dataset type. Supported values are:

| Value       | Description                                                              |
| ----------- | ------------------------------------------------------------------------ |
| `append`    | New data is appended to this dataset. Examples are logs or transactions. |
| `overwrite` | New data overwrites rows in this dataset. Examples are NFTs.             |

**`access`** \[optional]

Shared access to this dataset. Use **`*`** to give public access to all Spice users and organizations, or specify users/orgs.

| Key    | Description                                         |
| ------ | --------------------------------------------------- |
| `read` | A list of orgs/users or a single item array with \* |

```yaml
// Share access to all public users/orgs
access:
  read:
    - *
```

```
// Share access to specific users/orgs
access:
  read:
    - spicehq
    - lukekim
```

**`migrations`**

An ordered list of SQL migrations to execute to create or update this dataset.

[**`firecache`**](firecache.md)

Specifies the Spice Firecache properties of this dataset.

### Example definition

```yaml
# .spice/datasets/eth_recent_blocks.yaml
name: eth.recent_blocks
description: Ethereum blocks minted in the last 30 minutes.
type: append
access:
  read:
    - *
firecache:
  enabled: true
  trigger: number
  time_column: timestamp
```
