---
description: Firecache (beta)
---

# 🔥 Spice Firecache

{% hint style="info" %}
Spice Firecache is in beta for Design Partners. Get in touch for more info.
{% endhint %}

Spice Firecache is a real-time, in-memory SQL cache based on [DuckDB](https://duckdb.org/) that enables developers to cache Spice datasets for high concurrency, blazing fast SQL query up to 10x the performance of general SQL query.

The Spice platform completely manages the Spice Firecache data lifecycle, ensuring datasets are real-time updated on triggers like new blocks and with stale data being automatically evicted.

Firecaches are Spice app specific and only available to the Spice app they were deployed to.

## Enabling Firecache

Firecache is enabled per Dataset using a [Dataset manifest](../reference/specifications/dataset-and-view-yaml-specification/firecache.md). E.g.

```yaml
# .spice/datasets/eth.recent_blocks.yml
name: eth.recent_blocks
firecache:
  enabled: true
  trigger: block_number
  time_column: block_timestamp
```

Datasets with the `recent_` prefix are eligible to be self-serviced Firecached. If you would like other datasets to be cached, contact us.

Once enabled, the dataset must be deployed for the Firecache to be initialized.

See [datasets-and-views.md](datasets-and-views.md "mention") for full documentation on defining, managing and deploying datasets.

## Querying Firecache

Once Firecache enabled datasets have been deployed, they can be queried by the same interfaces as general SQL query, including with the SQL Query Editor in the [Spice.ai](https://spice.ai) portal, the HTTP API, and the Apache Arrow Flight API.

The Spice SDKs also have `Firequery()` methods in addition to the standard `Query()` to target Firecache.

### SQL Query Editor

The SQL Query Editor is the fastest way to get started with Spice Firecache queries, debugging queries, and iterating quickly. The Firecache SQL Query Editor be accessed by clicking on the **Firecache** tab after selecting **Playground** in the Spice.ai app navigation bar.

<figure><img src="../.gitbook/assets/Screenshot 2023-10-24 at 5.53.08 PM.png" alt=""><figcaption><p>The Firecache SQL Query Editor.</p></figcaption></figure>

The Dataset Reference pane will only list datasets available for query in Firecache.

See [sql-query-editor.md](../portal/sql-query-editor.md "mention") for further documentation on using the SQL Query Editor.

### Apache Arrow Flight API

For production applications, leveraging the high-performance [Apache Arrow Flight](../api/sql-query/apache-arrow-flight-api.md) endpoint is recommended. The Spice SDKs always access SQL queries and Firecache queries using Arrow Flight.

See [apache-arrow-flight-api.md](../api/sql-query/apache-arrow-flight-api.md "mention") for further documentation on using Apache Arrow Flight APIs.

### HTTP API

Spice Firecache is also accessible via a standard HTTP API.

See [http-api.md](../api/sql-query/http-api.md "mention") for further documentation on using the HTTP SQL API.
