---
description: All data currently available in Spice
---

# Datasets

{% hint style="success" %}
We add datasets every week, so this list is just the start. Get in touch on Discord to suggest more. **We're just getting started!**
{% endhint %}

### Datasets for SQL Query

Explore our SQL datasets organized by chain and data type, each with a representative table. Click the section header links for more information and complete table listings.

#### [Ethereum datasets](reference/sql-query-tables/sql-query-tables/)

| Blocks       | `eth.recent_blocks`       |
| ------------ | ------------------------- |
| Transactions | `eth.recent_transactions` |
| Logs         | `eth.recent_logs`         |
| Contracts    | `eth.contracts`           |
| Traces       | `eth.recent_traces`       |
| Withdrawals  | `eth.recent_withdrawals`  |

[**Ethereum Token datasets**](reference/sql-query-tables/sql-query-tables/token-tables.md)

| Contracts (erc20, erc721, erc1155)       | `eth.contracts`              |
| ---------------------------------------- | ---------------------------- |
| Tokens (erc20, erc721, erc1155)          | `eth.tokens`                 |
| Token Transfers (erc20, erc721, erc1155) | `eth.recent_token_transfers` |
| Token Mints (erc20, erc721, erc1155)     | `eth.recent_token_mints`     |

[**Ethereum NFT datasets**](reference/sql-query-tables/sql-query-tables/nft-tables.md)

| NFTs                                    | `eth.nfts`                         |
| --------------------------------------- | ---------------------------------- |
| NFT Contracts                           | `eth.nft_contracts`                |
| NFT Transfers (with optional hold time) | `eth.recent_nft_transfers`         |
| NFT Owners                              | `eth.nft_owners`                   |
| NFT Airdrop Transfers                   | `eth.recent_nft_airdrop_transfers` |

[**Ethereum Uniswap datasets**](reference/sql-query-tables/ethereum/uniswap-v2-tables.md)

| Uniswap V2 Pools                                     | `eth.uniswap_v2.pools`              |
| ---------------------------------------------------- | ----------------------------------- |
| Uniswap V2 Pool Statistics (reserves and price info) | `eth.uniswap_v2.pool_stats`         |
| Uniswap V2 Events (swaps, mints, burns, etc)         | `eth.uniswap_v2.recent_event_swaps` |
| Uniswap V3 Pools                                     | `eth.uniswap_v3.pools`              |
| Uniswap V3 Pool Statistics (reserves and price info) | `eth.uniswap_v3.pool_stats`         |
| Uniswap V3 Events (swaps, mints, burns, etc)         | `eth.uniswap_v3.recent_event_swaps` |

[**Ethereum Sushiswap datasets**](reference/sql-query-tables/ethereum/sushiswap-tables.md)

| Sushiswap Pools                                     | `eth.sushiswap.pools`              |
| --------------------------------------------------- | ---------------------------------- |
| Sushiswap Pool Statistics (reserves and price info) | `eth.sushiswap.pool_stats`         |
| Sushiswap Events (swaps, mints, burns, etc)         | `eth.sushiswap.recent_event_swaps` |

[**Ethereum Name Service (ENS) datasets**](reference/sql-query-tables/ethereum/token-tables-1.md)

| ENS Domains | `ens.domains` |
| ----------- | ------------- |

#### [Polygon datasets](reference/sql-query-tables/polygon/)

| Blocks       | `polygon.recent_blocks`       |
| ------------ | ----------------------------- |
| Transactions | `polygon.recent_transactions` |
| Logs         | `polygon.recent_logs`         |
| Contracts    | `polygon.contracts`           |
| Traces       | `polygon.recent_traces`       |

[**Polygon Token Datasets**](reference/sql-query-tables/polygon/token-tables.md)

| Contracts (erc20, erc721, erc1155)       | `polygon.contracts`              |
| ---------------------------------------- | -------------------------------- |
| Tokens (erc20, erc721, erc1155)          | `polygon.tokens`                 |
| Token Transfers (erc20, erc721, erc1155) | `polygon.recent_token_transfers` |
| Token Mints (erc20, erc721, erc1155)     | `polygon.recent_token_mints`     |

[**Polygon NFT Datasets**](reference/sql-query-tables/polygon/nft-tables.md)

| NFTs                                    | `polygon.nfts`                         |
| --------------------------------------- | -------------------------------------- |
| NFT Contracts                           | `polygon.nft_contracts`                |
| NFT Transfers (with optional hold time) | `polygon.recent_nft_transfers`         |
| NFT Owners                              | `polygon.nft_owners`                   |
| NFT Airdrop Transfers                   | `polygon.recent_nft_airdrop_transfers` |

[**Bitcoin datasets**](reference/sql-query-tables/bitcoin.md)

| Blocks              | `btc.recent_blocks`              |
| ------------------- | -------------------------------- |
| Transactions        | `btc.recent_transactions`        |
| Transaction Inputs  | `btc.recent_transaction_inputs`  |
| Transaction Outputs | `btc.recent_transaction_outputs` |

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
