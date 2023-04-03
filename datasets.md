---
description: All data currently available in Spice
---

# Datasets

{% hint style="info" %}
We add datasets every week, so this list is just the start. Get in touch on Discord to suggest more. **We're just getting started!**
{% endhint %}

### Datasets for SQL Query

#### [Ethereum datasets](reference/sql-query-tables/sql-query-tables/)

* Blocks
* Transactions
* Logs
* Contracts
* Traces

[**Ethereum Token datasets**](reference/sql-query-tables/sql-query-tables/token-tables.md)

* Contracts (erc20, erc721, erc1155)
* Tokens (erc20, erc721, erc1155)
* Token Transfers (erc20, erc721, erc1155)

[**Ethereum NFT datasets**](reference/sql-query-tables/sql-query-tables/nft-tables.md)

* NFT Contracts
* NFT Transfers (with optional hold time)
* NFT Owners
* NFT Airdrop Transfers

[**Ethereum Uniswap datasets**](reference/sql-query-tables/ethereum/uniswap-v2-tables.md)

* Uniswap V2 Pools (with optional details)
* Uniswap V2 Pool Statistics (reserve and price info)
* Uniswap V3 Pools (with optional details)
* Uniswap V3 Pool Statistics (reserve and price info)

[**Ethereum Sushiswap datasets**](reference/sql-query-tables/ethereum/sushiswap-tables.md)

* Sushiswap Pools (with optional details)
* Sushiswap Pool Statistics (reserve and price info)

****[**Ethereum Name Service (ENS) datasets**](reference/sql-query-tables/ethereum/token-tables-1.md)

* ENS Domains

#### [Polygon datasets](reference/sql-query-tables/polygon/)

* Blocks
* Transactions
* Logs
* Contracts
* Traces

****[**Polygon Token Datasets**](reference/sql-query-tables/polygon/token-tables.md)****

* Contracts (erc20, erc721, erc1155)
* Tokens (erc20, erc721, erc1155)
* Token Transfers (erc20, erc721, erc1155)

****[**Polygon NFT Datasets**](reference/sql-query-tables/polygon/nft-tables.md)****

* NFT Contracts
* NFT Transfers (with optional hold time)
* NFT Owners
* NFT Airdrop Transfers

****[**Bitcoin datasets**](reference/sql-query-tables/bitcoin.md)****

* Blocks
* Transactions
* Transaction Inputs
* Transaction Outputs

#### [Prices datasets](reference/sql-query-tables/prices/)

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
* Sushiswap
  * ETH-USDC
* UniswapV2
  * ETH-USDC
  * BTC-USDC

### Time-series Datasets

* [Spot/latest and historical prices](api/prices.md)
* [Ethereum gas fees](https://docs.spice.xyz/api/ethereum/gas-fees)
* [Ethereum blocks](https://docs.spice.xyz/api/ethereum/blocks)

### JSON RPC Methods

* See [JSON RPC Methods](datasets.md#time-series-datasets-1)
