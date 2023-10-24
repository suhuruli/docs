# Limitations

{% hint style="info" %}
See plan-specific limits in [Pricing](pricing/)
{% endhint %}

Spice.ai has the following limitations:

#### Global API Limits

* 500 row limit for HTTP API results (use the [Apache Arrow API](../api/sql-query/apache-arrow-flight-api.md) or the [Async HTTP API](../api/sql-query/http-api-1.md) for no limit).

#### Data Limitations (as of October 2023)

* 128-bit integer limit (while data can be uint256). We include both the 128-bit `DECIMAL(38)` type and `_hex` fields where the type is 256-bit.

#### Data format limitations

* List data cannot be downloaded as CSV from the Portal
  * If you wish to download list data as CSV, you should use the [flatten](https://docs.dremio.com/software/sql-reference/sql-functions/functions/FLATTEN/) operator first:
    * `select topics from eth.logs limit 1` will **NOT** be able to be downloaded as CSV
    * `select flatten(topics) from eth.logs limit 1` _will_ be able to be downloaded as CSV
