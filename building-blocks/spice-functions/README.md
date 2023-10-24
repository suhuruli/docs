---
description: Spice Functions (beta)
---

# Spice Functions

{% hint style="info" %}
Spice Functions is in beta and initially available for Design Partners. Get in touch for more info.
{% endhint %}

Spice Functions is a hosted compute experience that enables developers to write code in their preferred language and run it on the Spice platform, co-located with Spice data.

Spice Functions enables new use-cases for developers building intelligent applications with time-series and blockchain data, including flexible data transformation and aggregations, AI/ML data preparation, alerting, filtering, and integrations with other services.

Functions can be implemented in [Python](python.md) or [Go](golang.md), with support for Node.js and Rust coming.

See the [Spice Functions Roadmap](roadmap.md) for upcoming features.

## Creating an output dataset

Spice Functions currently requires a designated [dataset](../datasets-and-views.md) to store function output.

Follow the [Datasets and Views](../datasets-and-views.md) guide to create a new dataset. In addition, add a migration to define the dataset schema and create the table.

<details>

<summary>Example output dataset</summary>

```yaml
# .spice/datasets/hello_world.yml
name: {orgName}.{appName}.hello_world
type: append
migrations:
  - name: create_table
    sql: |
      CREATE TABLE IF NOT EXISTS {orgName}.{appName}.hello_world (
        block_number BIGINT PRIMARY KEY,
        greeting TEXT
      )
```

Replace `{orgName}` and `{appName}` with the values for your specific org and app.

</details>

Optionally specifying a primary key will help enforce data integrity and enables the dataset rows to be updatable.

Datasets defined in a Spice app will be available and queryable from all apps in the [organization](../../portal/organizations.md).

Once you've created the YAML and committed to your repository, follow the same steps outlined in [Datasets and Views](../datasets-and-views.md) to sync from GitHub and deploy the dataset to the Spice platform.

## Creating a function

A Spice Function is defined by creating a directory in the Spice app's connected GitHub repository and adding a [`function.yaml`](../../reference/specifications/spice-functions-yaml-specification/) file.

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

A [Python](python.md) invocation handler method has the following signature:

```python
def process(context: dict, 
            duckdb: duckdb.DuckDBPyConnection, 
            spice_client: spicepy.Client):
```

* `context`: A dictionary with context variables, E.g. `block_number` and `block_hash`
* `duckdb`: A connection to the Spice Function's DuckDB instance.
* `spice_client`: A [spicepy](https://github.com/spiceai/spicepy) client that is pre-initialized with the Spice app's API Key.

The handler method will be called on each triggered event.

See [Golang](golang.md) for defining a Go function handler.

Each Spice Function is provisioned with a private, dedicated, and persisted DuckDB instance accessed by the `duckdb` parameter. The DuckDB instance can be used to query, persist, process, and analyze data across function invocations.

To load and persist data into the output dataset, first create a staging table in the DuckDB instance, in the `output` namespace with the same schema used in the dataset creation. E.g.

```python
# Create output dataset staging table in DuckDB
duckdb.sql("""CREATE TABLE IF NOT EXISTS output.hello_world (
  block_number BIGINT,
  greeting TEXT
  )""")
```

Data inserted into the staging `output.{output_dataset}` table will be loaded and merged into the output dataset. For example:

```python
duckdb.sql(f"INSERT INTO output.hello_world VALUES ({context['block_number']}, 'Hello!')")
```

The staging `output.{output_dataset}` table is reset upon each function invocation and thus will be empty on each function invocation.

{% hint style="info" %}
Rows inserted into the duckdb **`output.{output_dataset}`** table with an existing primary key value will be updated in-place.
{% endhint %}

See [Python](python.md) and [Go](golang.md) for full example code.

## Sync with GitHub

Once your function is committed to the GitHub repository, navigate to the **Functions** section of your Spice app. The newly defined function will appear in the functions list.

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-24 at 6.13.27 PM.png" alt=""><figcaption><p>List of synced Functions</p></figcaption></figure>

## Deploy the Function

Click the function **Deploy** button. It may take a few moments as the code is packaged and deployed for use within the platform.

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-24 at 9.10.58 PM.png" alt=""><figcaption><p>Deployed function hello_world is now running.</p></figcaption></figure>

## View Function details

Clicking the function name will show its details along with it's recent deployments.

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-24 at 9.11.55 PM.png" alt=""><figcaption><p>Function details page</p></figcaption></figure>

## View Function deployments

To view the history of deployments for this function, navigate to the Deployments tab.

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-24 at 9.13.28 PM.png" alt=""><figcaption><p>Function deployments</p></figcaption></figure>

## View Function executions

Clicking the Executions tab in the Function details page will show the recent function executions.

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-24 at 9.14.09 PM.png" alt=""><figcaption><p>Function executions page</p></figcaption></figure>

## View Function execution logs

Click on the UUID of a function execution to view the logs from a function execution, including its standard output, standard error and exit code.

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-24 at 9.14.48 PM.png" alt=""><figcaption><p>Logs from a function execution</p></figcaption></figure>

## Query the Function output dataset

If data was inserted into the output dataset, upon successful function execution, it will be available for query in the Playground from the output dataset you defined for your function, i.e. `"{orgName}".{appName}.hello_world`.

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-24 at 9.16.28 PM.png" alt=""><figcaption><p>Querying for hello_world's output</p></figcaption></figure>
