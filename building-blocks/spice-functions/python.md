---
description: Creating a Spice Function in Python
---

# Python

### Function Handlers

In the `function.yaml` , code execution runtime and invocation handler is defined.

<details>

<summary>Example <code>function.yaml</code> for a Python function</summary>

```yaml
# hello_world/function.yaml
output_datasets: 
  - {orgName}.{appName}.hello_world
# This will trigger the function to execute on every new Ethereum block.
triggers:
  - path: eth
# This selects the runtime that will execute your code.
runtime: python3.11
# For Python, handler is [script_name].[method]
# The below will invoke a method `process` in a file `spice_function.py`.
handler: spice_function.process
```

Replace `{orgName}` and `{appName}` with the values for your specific org and app.

</details>

See [Spice Functions YAML Specification](../../reference/specifications/spice-functions-yaml-specification/) for the full YAML schema.

### Function Handlers

A Python invocation handler method has the following signature:

```python
def process(context: dict, 
            duckdb: duckdb.DuckDBPyConnection, 
            spice_client: spicepy.Client):
```

* `context`: A dictionary with context variables, E.g. `block_number` and `block_hash`
* `duckdb`: A connection to the Spice Function's DuckDB instance.
* `spice_client`: A [spicepy](https://github.com/spiceai/spicepy) client that is pre-initialized with the Spice app's API Key.

The handler method will be called on each triggered event.

### Dependencies

Python dependencies can be specified by placing a `requirements.txt` adjacent to the code importing the dependencies.

The Python function runtime comes pre-loaded with these modules:

* [spicepy](https://github.com/spiceai/spicepy)
* [pyarrow](https://pypi.org/project/pyarrow/)
* [duckdb](https://duckdb.org/docs/api/python/overview)
* [pandas](https://pypi.org/project/pandas/)
* [numpy](https://pypi.org/project/numpy/)
* [pyyaml](https://pypi.org/project/PyYAML/)

Currently, Python modules that depend on compiled C extensions are not supported to be defined in requirements.txt. A request for a particular missing dependency may be made on Discord.

### Example Function

An example Python function that will produce the same outputs shown above:

```python
# hello_world/spice_function.py
import duckdb
import spicepy

def process(context: dict, 
            duckdb: duckdb.DuckDBPyConnection, 
            spice_client: spicepy.Client):
  duckdb.sql(f"INSERT INTO output.hello_world VALUES ({context['block_number']}, 'Hello!')")

  print("Hello, World!")
```
