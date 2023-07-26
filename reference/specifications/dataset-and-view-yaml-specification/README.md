# Dataset & View YAML Specification

Spice Datasets and Views are defined in YAML. To create a Dataset or View, add a dataset YAML to the `.spice/datasets` path of the connected [GitHub repository](../../../portal/apps/link-github-repository-beta.md).

### **YAML Schema Reference**

**`name`**

The name of the dataset. Only alpha characters and underscores are supported with no spaces.

**`type`**

The dataset type. Supported values are:

| Value       | Description                                                              |
| ----------- | ------------------------------------------------------------------------ |
| `append`    | New data is appended to this dataset. Examples are logs or transactions. |
| `overwrite` | New data overwrites rows in this dataset. Examples are NFTs.             |

**`migrations`**

An ordered list of SQL migrations to execute to create or update this dataset.

[**`firecache`**](firecache.md)

Specifies the Spice Firecache properties of this dataset.

### Example definition

```yaml
# .spice/datasets/eth_recent_blocks.yaml
name: eth.recent_blocks
type: append
firecache:
  enabled: true
  trigger: number
  time_column: timestamp
```
