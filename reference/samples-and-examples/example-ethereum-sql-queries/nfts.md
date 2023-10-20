---
description: Example queries that use the Ethereum and Polygon NFTs datasets
---

# NFTs

Querying the NFTs datasets enable use cases like tracking recent transfer of NFTs, referencing all NFTs from a single collection like from Bored Ape or Aavegotchi, and finding all current owners of Bored Apes. Copy example queries directly into your Spice.ai Playground to get started in seconds.&#x20;

### Recent NFT Transfers

Transfers of NFTs that conform to both ERC721 and ERC1155 token standards.

{% tabs %}
{% tab title="Ethereum" %}
```sql
SELECT * FROM eth.recent_nft_transfers
ORDER BY block_number DESC, token_address, token_id
LIMIT 10
```
{% endtab %}

{% tab title="Polygon" %}
```sql
SELECT * FROM polygon.recent_nft_transfers
ORDER BY block_number DESC, token_address, token_id
LIMIT 10
```
{% endtab %}
{% endtabs %}

### All NFTs from a single collection

Ethereum: All Bored Ape Yacht Club NFTs.

Polygon: All Aavegotchi NFTs.

{% tabs %}
{% tab title="Ethereum" %}
```sql
SELECT * FROM eth.nfts
WHERE address = '0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d' -- BAYC
ORDER BY CAST(token_id AS NUMERIC)
```
{% endtab %}

{% tab title="Polygon" %}
```sql
SELECT * FROM polygon.nfts
WHERE address = '0x86935f11c86623dec8a25696e1c19a8659cbf95d' -- Aavegotchi
ORDER BY CAST(token_id AS NUMERIC)
```
{% endtab %}
{% endtabs %}

### Current owners of all NFTs from a collection

Ethereum: Current owners of all Bored Ape Yacht Club NFTs.

Polygon: Current owners of all Aavegotchi NFTs.

{% tabs %}
{% tab title="Ethereum" %}
```sql
SELECT * FROM eth.nft_owners
WHERE token_address = '0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d' -- BAYC
ORDER BY CAST(token_id AS NUMERIC)
```
{% endtab %}

{% tab title="Polygon" %}
```sql
SELECT * FROM polygon.nft_owners
WHERE token_address = '0x86935f11c86623dec8a25696e1c19a8659cbf95d' -- Aavegotchi
ORDER BY CAST(token_id AS NUMERIC)
```
{% endtab %}
{% endtabs %}

### Number of smart contracts with NFTs

Returns how many NFT smart contracts exist

{% tabs %}
{% tab title="Ethereum" %}
```sql
SELECT COUNT(*) as "num_contracts"
FROM eth.nft_contracts
```
{% endtab %}

{% tab title="Polygon" %}
```sql
SELECT COUNT(*) as "num_contracts"
FROM polygon.nft_contracts
```
{% endtab %}
{% endtabs %}
