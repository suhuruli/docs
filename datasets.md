---
description: All data currently available in Spice
---

# Datasets

{% hint style="success" %}
We add datasets every week, so this list is just the start. Get in touch on Discord to suggest more. **We're just getting started!**
{% endhint %}

### Datasets for SQL Query

Explore our SQL datasets organized by chain and data type, each with a representative table. Click the section header links for more information and complete table listings.

{% hint style="info" %}
For most tables, prefix `recent_` to access a faster version with data from the past 30 minutes. i.e. `eth.blocks` -> `eth.recent_blocks`
{% endhint %}

#### [Ethereum datasets](reference/sql-query-tables/sql-query-tables/)

| Blocks       | `eth.blocks`       |
| ------------ | ------------------ |
| Transactions | `eth.transactions` |
| Logs         | `eth.logs`         |
| Contracts    | `eth.contracts`    |
| Traces       | `eth.traces`       |

[**Ethereum Token datasets**](reference/sql-query-tables/sql-query-tables/token-tables.md)

| Contracts (erc20, erc721, erc1155)       | `eth.contracts`       |
| ---------------------------------------- | --------------------- |
| Tokens (erc20, erc721, erc1155)          | `eth.tokens`          |
| Token Transfers (erc20, erc721, erc1155) | `eth.token_transfers` |
| Token Mints (erc20, erc721, erc1155)     | `eth.token_mints`     |

[**Ethereum NFT datasets**](reference/sql-query-tables/sql-query-tables/nft-tables.md)

| NFTs                                    | `eth.nfts`                  |
| --------------------------------------- | --------------------------- |
| NFT Contracts                           | `eth.nft_contracts`         |
| NFT Transfers (with optional hold time) | `eth.nft_transfers`         |
| NFT Owners                              | `eth.nft_owners`            |
| NFT Airdrop Transfers                   | `eth.nft_airdrop_transfers` |

[**Ethereum Uniswap datasets**](reference/sql-query-tables/ethereum/uniswap-v2-tables.md)

| Uniswap V2 Pools                                     | `eth.uniswap_v2.pools`       |
| ---------------------------------------------------- | ---------------------------- |
| Uniswap V2 Pool Statistics (reserves and price info) | `eth.uniswap_v2.pool_stats`  |
| Uniswap V2 Events (swaps, mints, burns, etc)         | `eth.uniswap_v2.event_swaps` |
| Uniswap V3 Pools                                     | `eth.uniswap_v3.pools`       |
| Uniswap V3 Pool Statistics (reserves and price info) | `eth.uniswap_v3.pool_stats`  |
| Uniswap V3 Events (swaps, mints, burns, etc)         | `eth.uniswap_v3.event_swaps` |

[**Ethereum Sushiswap datasets**](reference/sql-query-tables/ethereum/sushiswap-tables.md)

| Sushiswap Pools                                     | `eth.sushiswap.pools`       |
| --------------------------------------------------- | --------------------------- |
| Sushiswap Pool Statistics (reserves and price info) | `eth.sushiswap.pool_stats`  |
| Sushiswap Events (swaps, mints, burns, etc)         | `eth.sushiswap.event_swaps` |

****[**Ethereum Name Service (ENS) datasets**](reference/sql-query-tables/ethereum/token-tables-1.md)

| ENS Domains | `ens.domains` |
| ----------- | ------------- |

#### [Polygon datasets](reference/sql-query-tables/polygon/)

| Blocks       | `polygon.blocks`       |
| ------------ | ---------------------- |
| Transactions | `polygon.transactions` |
| Logs         | `polygon.logs`         |
| Contracts    | `polygon.contracts`    |
| Traces       | `polygon.traces`       |

****[**Polygon Token Datasets**](reference/sql-query-tables/polygon/token-tables.md)****

| Contracts (erc20, erc721, erc1155)       | `polygon.contracts`       |
| ---------------------------------------- | ------------------------- |
| Tokens (erc20, erc721, erc1155)          | `polygon.tokens`          |
| Token Transfers (erc20, erc721, erc1155) | `polygon.token_transfers` |
| Token Mints (erc20, erc721, erc1155)     | `polygon.token_mints`     |

****[**Polygon NFT Datasets**](reference/sql-query-tables/polygon/nft-tables.md)****

| NFTs                                    | `polygon.nfts`                  |
| --------------------------------------- | ------------------------------- |
| NFT Contracts                           | `polygon.nft_contracts`         |
| NFT Transfers (with optional hold time) | `polygon.nft_transfers`         |
| NFT Owners                              | `polygon.nft_owners`            |
| NFT Airdrop Transfers                   | `polygon.nft_airdrop_transfers` |

****[**Bitcoin datasets**](reference/sql-query-tables/bitcoin.md)****

| Blocks              | `btc.blocks`              |
| ------------------- | ------------------------- |
| Transactions        | `btc.transactions`        |
| Transaction Inputs  | `btc.transaction_inputs`  |
| Transaction Outputs | `btc.transaction_outputs` |

#### [Prices datasets](reference/sql-query-tables/prices/)

Query for BTC, ETH and LTC prices in SQL with data sourced from several sources

|                                       |              |
| ------------------------------------- | ------------ |
| ETH prices (OHLC @ 1 min granularity) | `prices.eth` |
| BTC prices (OHLC @ 1 min granularity) | `prices.btc` |
| LTC prices (OHLC @ 1 min granularity) | `prices.ltc` |

{% hint style="info" %}
For access to spot/historical prices on thousands of pairs, try our [time-series Prices API](api/prices.md).
{% endhint %}

#### [Chainlink datasets](reference/sql-query-tables/chainlink/)

* Prices
  * Prices observed by oracle data feeds on the chainlink network

### Time-series Datasets

* [Ethereum blocks](https://docs.spice.xyz/api/ethereum/blocks)
* [Ethereum gas fees](https://docs.spice.xyz/api/ethereum/gas-fees)

#### [Spot/latest and historical prices](api/prices.md)

* Binance
  * Spot/latest prices for all pairs traded on Binance.
  * Historical OHLC prices at 1-min granularity for all pairs.
* Coinbase
  * Spot/latest prices for all pairs traded on Coinbase.
  * Historical OHLC prices at 1-min granularity for all pairs.
* Gemini
  * Spot/latest prices for all pairs traded on Gemini.
  * Partial historical OHLC prices at 1-min granularity for all pairs.
* Coinmarket Cap
  * Spot/latest prices for all pairs tracked by Coinmarket Cap
  * Historical prices in the last year for all pair tracked by Coinmarket Cap

### JSON RPC Methods

* See [JSON RPC Methods](datasets.md#time-series-datasets-1)
