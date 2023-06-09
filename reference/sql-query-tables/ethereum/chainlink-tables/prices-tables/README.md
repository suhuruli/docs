---
description: Ethereum Chainlink Price tables available in SQL query
---

# Prices Tables

#### Prices specific tables

| Table name                                               | Description                                                                                        |
| -------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [`eth.chainlink.prices`](eth.chainlink.prices.md)        | Prices per price oracle data feeds on the ethereum network                                         |
| [`eth.chainlink.recent_prices`](eth.chainlink.prices.md) | Prices per price oracle data feeds on the ethereum network from the last 30min (\~last 128 blocks) |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE eth.chainlink.prices;
```

| Column name        | Description                                                                           |
| ------------------ | ------------------------------------------------------------------------------------- |
| `oracle_address`   | The address of the oracle which emitted the latest answer for the price of this asset |
| `asset_address`    | The address of the asset which the latest answer for the price refers to              |
| `price_wei`        | The latest answer for the price of the asset in WEI                                   |
| `block_timestamp`  | The block timestamp the answer was emitted on                                         |
| `block_number`     | The block number the answer was emitted on                                            |
| `block_hash`       | The block hash the answer was emitted on                                              |
| `transaction_hash` | The transaction hash the answer was emitted on                                        |

We currently support price feeds for the following assets:

| asset\_address                               | name                    | symbol |
| -------------------------------------------- | ----------------------- | ------ |
| `0xd533a949740bb3306d119cc777fa900ba034cd52` | Curve DAO Token         | CRV    |
| `0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48` | USD Coin                | USDC   |
| `0x1494ca1f11d487c2bbe4543e90080aeba4ba3c2b` | DefiPulse Index         | DPI    |
| `0xa693b19d2931d498c5b318df961919bb4aee87a5` | UST                     | UST    |
| `0x0f5d2fb29fb7d3cfee444a200298f468908cc942` | Decentraland MANA       | MANA   |
| `0xae7ab96520de3a18e5e111b5eaab095312d7fe84` | Liquid staked Ether 2.0 | stETH  |
| `0x514910771af9ca656af840dff83e8264ecf986ca` | ChainLink Token         | LINK   |
| `0xba100000625a3754423978a60c9317c58a424e3d` | Balancer                | BAL    |
| `0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c` | Enjin Coin              | ENJ    |
| `0xdac17f958d2ee523a2206206994597c13d831ec7` | Tether USD              | USDT   |
| `0x2260fac5e5542a773aa44fbcfedf7c193bc2c599` | Wrapped BTC             | WBTC   |
| `0x9f8f72aa9304c8b593d555f12ef6589cc3a579a2` | Maker                   | MKR    |
| `0x956f47f50a910163d8bf957cf5846d573e7f87ca` | Fei USD                 | FEI    |
| `0x1f9840a85d5af5bf1d1762f925bdaddc4201f984` | Uniswap                 | UNI    |
| `0x8e870d67f660d95d5be530380d0ec0bd388289e1` | Pax Dollar              | USDP   |
| `0xdd974d5c2e2928dea5f71b9825b8b646686bd200` | Kyber Network Crystal   | KNC    |
| `0x7fc66500c84a76ad7e9c93437bfc5ac33e2ddae9` | Aave Token              | AAVE   |
| `0xe41d2489571d322189246dafa5ebde1f4699f498` | 0x Protocol Token       | ZRX    |
| `0x4fabb145d64652a948d72533023f6e7a623c7c53` | Binance USD             | BUSD   |
| `0x8798249c2e607446efb7ad49ec89dd1865ff4272` | SushiBar                | xSUSHI |
| `0xd5147bc8e386d91cc5dbe72099dac6c9b99276f5` | renFIL                  | renFIL |
| `0x111111111117dc0aa78b770fa6a738034120c302` | 1INCH Token             | 1INCH  |
| `0x0d8775f648430679a709e98d2b0cb6250d2887ef` | Basic Attention Token   | BAT    |
| `0x0bc529c00c6401aef6d220be8c6ea1667f6ad93e` | yearn.finance           | YFI    |
| `0x6b175474e89094c44da98b954eedeac495271d0f` | Dai Stablecoin          | DAI    |
| `0x853d955acef822db058eb8505911ed77f175b99e` | Frax                    | FRAX   |
| `0xd46ba6d942050d489dbd938a2c909a5d5039a161` | Ampleforth              | AMPL   |
| `0x03ab458634910aad20ef5f1c8ee96f1d6ac54919` | Rai Reflex Index        | RAI    |
| `0x57ab1ec28d129707052df4df418d58a2d46d5f51` | Synth sUSD              | sUSD   |
| `0x408e41876cccdc0f92210600ef50372656052a38` | Republic Token          | REN    |
| `0xc011a73ee8576fb46f5e1c5751ca3b9fe0af2a6f` | Synthetix Network Token | SNX    |
| `0x4e3fbd56cd56c3e72c1403e103b45db9da5b9d2b` | Convex Token            | CVX    |
| `0x0000000000085d4780b73119b644ae5ecd22b376` | TrueUSD                 | TUSD   |
