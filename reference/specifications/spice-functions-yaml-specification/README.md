# Spice Functions YAML Specification

Spice Functions configuration and metadata is defined in YAML. To create a Spice Function, add a `function.yaml` manifest file to a connected [GitHub repository](../../../portal/apps/connect-github-repository.md).

`function.yaml` should be co-located with the function code in a subdirectory from the root of the repository.

### YAML Schema Reference

**`output_dataset`**

The [Dataset](../../../building-blocks/datasets-and-views.md) this function's output will populate.

**`runtime`**

The execution runtime for the function. Supported runtimes are:

| Runtime      | Description |
| ------------ | ----------- |
| `python3.11` | Python 3.11 |
| `go1.x`      | go1.x       |

**`handler`**

The entry point file/module and code function/method that handles triggered executions.

<table><thead><tr><th width="145.33333333333331">Runtime</th><th>Format</th><th>Example</th></tr></thead><tbody><tr><td>Python</td><td><code>filename.function_name</code></td><td><code>my_python_file.process</code></td></tr><tr><td>Go</td><td><code>main()</code> in <code>main.go</code></td><td></td></tr></tbody></table>

[**`triggers`**](triggers.md)

Specifies the trigger conditions of the function.

### Example definition

```yaml
# nft_mint_counter/function.yaml
output_dataset: nft_mint_counter
triggers:
  - path: eth
runtime: python3.11
handler: spice_function.process
```
