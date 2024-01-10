---
description: Exporting Firecache for import into DuckDB.
---

# DuckDB Export Database

The underlying DuckDB database behind Firecache can be exported and downloaded via the `/firecache/export` API, which can be useful for local analysis and debugging.

{% hint style="danger" %}
Warning: Running export on a high-load Firecache can significantly affect its performance during the export and should be used with caution.
{% endhint %}

`POST` to the API to download the archive as Parquet. E.g.

```bash
curl --request POST \
  --url https://data.spiceai.io/v1/firecache/export \
  --header 'X-API-Key: <Your API Key>'
  --output firecache.zip
```

Then unzip the archive and import into DuckDB.

```sql
// Run in DuckDB
IMPORT DATABASE 'firecache';
```

Options can be passed via the body E.g.

```bash
curl --request POST \
  --url https://data.spiceai.io/v1/firecache/export \
  --header 'Content-Type: application/json' \
  --header 'X-API-Key: <Your API Key>'
  --data '{
	"format": "csv"
}'
  --output firecache_csv.zip
```

See the [DuckDB import/export documentation](https://duckdb.org/docs/sql/statements/export) for all format/compression options and more information on importing to DuckDB.

{% swagger method="post" path="/export" baseUrl="https://data.spiceai.io/v1/firecache" summary="Firecache Export Database" %}
{% swagger-description %}
Export the underlying DuckDB Database as CSV or Parquet for import into DuckDB.
{% endswagger-description %}

{% swagger-parameter in="body" name="format" %}
The export format. Valid values are `csv` or `parquet`. Defaults to `parquet`.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="compression" %}
Compression option for Parquet exports. Valid values are `uncompressed`,  `snappy`, `gzip` or `zstd`. Defaults to `zstd`.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="An `application/zip` binary stream of the exported archive." %}

{% endswagger-response %}
{% endswagger %}

