# Beacon HTTP API

The **`https://data.spiceai.io/goerli/beacon`** API is compatible with the read-only GET requests from the [Beacon Node API specification](https://ethereum.github.io/beacon-APIs/#/Beacon).

#### Authentication

All requests should specify the Spice API Key by adding a header with `X-API-KEY` or appending `?api_key=[apikey]` to the URL suffix.

{% tabs %}
{% tab title="Header API Key Example" %}
```bash
curl https://data.spiceai.io/goerli/beacon/goerli/v1/beacon/genesis \
  --header 'X-API-Key: [api-key]'
```
{% endtab %}

{% tab title="Query API Key Example" %}
```bash
curl https://data.spiceai.io/goerli/beacon/goerli/v1/beacon/genesis?api_key=[api_key]
```
{% endtab %}
{% endtabs %}

#### Beacon APIs

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/genesis" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/states/{state_id}/root" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/states/{state_id}/fork" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/states/{state_id}/finality_checkpoints" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/states/{state_id}/validators" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/states/{state_id}/validators/{validator_id}" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/states/{state_id}/validator_balances" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/states/{state_id}/committees" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/states/{state_id}/sync_committees" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/headers" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/headers/{block_id}" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v2/beacon/blocks/{block_id}" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/blocks/{block_id}/root" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/blocks/{block_id}/attestations" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/pool/attestations" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/pool/attester_slashings" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/pool/proposer_slashings" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/beacon-node-goerli-oapi.json" path="/eth/v1/beacon/pool/voluntary_exits" method="get" %}
[beacon-node-goerli-oapi.json](../../.gitbook/assets/beacon-node-goerli-oapi.json)
{% endswagger %}
