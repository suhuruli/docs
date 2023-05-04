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

| Blocks       | `eth.blocks`       | `eth.recent_blocks`       |
| ------------ | ------------------ | ------------------------- |
| Transactions | `eth.transactions` | `eth.recent_transactions` |
| Logs         | `eth.logs`         | `eth.recent_logs`         |
| Contracts    | `eth.contracts`    |                           |
| Traces       | `eth.traces`       | `eth.recent_traces`       |
| Withdrawals  | `eth.withdrawals`  | `eth.recent_withdrawals`  |

[**Ethereum Token datasets**](reference/sql-query-tables/sql-query-tables/token-tables.md)

| Contracts (erc20, erc721, erc1155)       | `eth.contracts`       |                              |
| ---------------------------------------- | --------------------- | ---------------------------- |
| Tokens (erc20, erc721, erc1155)          | `eth.tokens`          |                              |
| Token Transfers (erc20, erc721, erc1155) | `eth.token_transfers` | `eth.recent_token_transfers` |
| Token Mints (erc20, erc721, erc1155)     | `eth.token_mints`     | `eth.recent_token_mints`     |

[**Ethereum NFT datasets**](reference/sql-query-tables/sql-query-tables/nft-tables.md)

| NFTs                                    | `eth.nfts`                  |                                    |
| --------------------------------------- | --------------------------- | ---------------------------------- |
| NFT Contracts                           | `eth.nft_contracts`         |                                    |
| NFT Transfers (with optional hold time) | `eth.nft_transfers`         | `eth.recent_nft_transfers`         |
| NFT Owners                              | `eth.nft_owners`            |                                    |
| NFT Airdrop Transfers                   | `eth.nft_airdrop_transfers` | `eth.recent_nft_airdrop_transfers` |

[**Ethereum Uniswap datasets**](reference/sql-query-tables/ethereum/uniswap-v2-tables.md)

| Uniswap V2 Pools                                     | `eth.uniswap_v2.pools`       |                                     |
| ---------------------------------------------------- | ---------------------------- | ----------------------------------- |
| Uniswap V2 Pool Statistics (reserves and price info) | `eth.uniswap_v2.pool_stats`  |                                     |
| Uniswap V2 Events (swaps, mints, burns, etc)         | `eth.uniswap_v2.event_swaps` | `eth.uniswap_v2.recent_event_swaps` |
| Uniswap V3 Pools                                     | `eth.uniswap_v3.pools`       |                                     |
| Uniswap V3 Pool Statistics (reserves and price info) | `eth.uniswap_v3.pool_stats`  |                                     |
| Uniswap V3 Events (swaps, mints, burns, etc)         | `eth.uniswap_v3.event_swaps` | `eth.uniswap_v3.recent_event_swaps` |

[**Ethereum Sushiswap datasets**](reference/sql-query-tables/ethereum/sushiswap-tables.md)

| Sushiswap Pools                                     | `eth.sushiswap.pools`       |                                    |
| --------------------------------------------------- | --------------------------- | ---------------------------------- |
| Sushiswap Pool Statistics (reserves and price info) | `eth.sushiswap.pool_stats`  |                                    |
| Sushiswap Events (swaps, mints, burns, etc)         | `eth.sushiswap.event_swaps` | `eth.sushiswap.recent_event_swaps` |

[**Ethereum Name Service (ENS) datasets**](reference/sql-query-tables/ethereum/token-tables-1.md)

| ENS Domains | `ens.domains` |
| ----------- | ------------- |

[**Ethereum Beacon Chain datasets**](reference/sql-query-tables/sql-query-tables/beacon-chain-tables.md)

|                          |                                       |                                              |
| ------------------------ | ------------------------------------- | -------------------------------------------- |
| Validators               | `eth.beacon.validators`               |                                              |
| Slots                    | `eth.beacon.slots`                    | `eth.beacon.recent_slots`                    |
| Attestations             | `eth.beacon.attestations`             | `eth.beacon.recent_attestations`             |
| Deposits                 | `eth.beacon.deposits`                 | `eth.beacon.recent_deposits`                 |
| Voluntary Exits          | `eth.beacon.voluntary_exits`          | `eth.beacon.recent_voluntary_exits`          |
| Attester Slashings       | `eth.beacon.attester_slashings`       | `eth.beacon.recent_attester_slashings`       |
| Proposer Slashings       | `eth.beacon.proposer_slashings`       | `eth.beacon.recent_proposer_slashings`       |
| BLS To Execution Changes | `eth.beacon.bls_to_execution_changes` | `eth.beacon.recent_bls_to_execution_changes` |
| Withdrawals              | `eth.beacon.withdrawals`              | `eth.beacon.recent_withdrawals`              |

#### [Ethereum Aave V2 datasets](reference/sql-query-tables/sql-query-tables/aave-v2-tables.md)

|                          |                                  |                                         |
| ------------------------ | -------------------------------- | --------------------------------------- |
| Loans (historical)       | `eth.aave_v2.loan_updates`       | `eth.aave_v2.recent_loan_updates`       |
| Collateral (historical)  | `eth.aave_v2.collateral_updates` | `eth.aave_v2.recent_collateral_updates` |
| Loans (latest view)      | `eth.aave_v2.loans`              |                                         |
| Collateral (latest view) | `eth.aave_v2.collateral`         |                                         |

#### [Goerli Datasets](reference/sql-query-tables/sql-query-tables-1/)

| Blocks       | `goerli.blocks`       | `goerli.recent_blocks`       |
| ------------ | --------------------- | ---------------------------- |
| Transactions | `goerli.transactions` | `goerli.recent_transactions` |
| Logs         | `goerli.logs`         | `goerli.recent_logs`         |
| Contracts    | `goerli.contracts`    |                              |
| Traces       | `goerli.traces`       | `goerli.recent_traces`       |
| Withdrawals  | `goerli.withdrawals`  | `goerli.recent_withdrawals`  |

#### [Goerli Token Datasets](reference/sql-query-tables/sql-query-tables-1/token-tables.md)

| Contracts (erc20, erc721, erc1155)       | `goerli.contracts`       |                                 |
| ---------------------------------------- | ------------------------ | ------------------------------- |
| Tokens (erc20, erc721, erc1155)          | `goerli.tokens`          |                                 |
| Token Transfers (erc20, erc721, erc1155) | `goerli.token_transfers` | `goerli.recent_token_transfers` |
| Token Mints (erc20, erc721, erc1155)     | `goerli.token_mints`     | `goerli.recent_token_mints`     |

#### [Goerli Beacon Chain Datasets](reference/sql-query-tables/sql-query-tables-1/beacon-chain-tables.md)

|                          |                                          |                                                 |
| ------------------------ | ---------------------------------------- | ----------------------------------------------- |
| Validators               | `goerli.beacon.validators`               |                                                 |
| Slots                    | `goerli.beacon.slots`                    | `goerli.beacon.recent_slots`                    |
| Attestations             | `goerli.beacon.attestations`             | `goerli.beacon.recent_attestations`             |
| Deposits                 | `goerli.beacon.deposits`                 | `goerli.beacon.recent_deposits`                 |
| Voluntary Exits          | `goerli.beacon.voluntary_exits`          | `goerli.beacon.recent_voluntary_exits`          |
| Attester Slashings       | `goerli.beacon.attester_slashings`       | `goerli.beacon.recent_attester_slashings`       |
| Proposer Slashings       | `goerli.beacon.proposer_slashings`       | `goerli.beacon.recent_proposer_slashings`       |
| BLS To Execution Changes | `goerli.beacon.bls_to_execution_changes` | `goerli.beacon.recent_bls_to_execution_changes` |
| Withdrawals              | `goerli.beacon.withdrawals`              | `goerli.beacon.recent_withdrawals`              |

#### [Polygon datasets](reference/sql-query-tables/polygon/)

| Blocks       | `polygon.blocks`       | `polygon.recent_blocks`       |
| ------------ | ---------------------- | ----------------------------- |
| Transactions | `polygon.transactions` | `polygon.recent_transactions` |
| Logs         | `polygon.logs`         | `polygon.recent_logs`         |
| Contracts    | `polygon.contracts`    |                               |
| Traces       | `polygon.traces`       | `polygon.recent_traces`       |

[**Polygon Token Datasets**](reference/sql-query-tables/polygon/token-tables.md)

| Contracts (erc20, erc721, erc1155)       | `polygon.contracts`       |                                  |
| ---------------------------------------- | ------------------------- | -------------------------------- |
| Tokens (erc20, erc721, erc1155)          | `polygon.tokens`          |                                  |
| Token Transfers (erc20, erc721, erc1155) | `polygon.token_transfers` | `polygon.recent_token_transfers` |
| Token Mints (erc20, erc721, erc1155)     | `polygon.token_mints`     | `polygon.recent_token_mints`     |

[**Polygon NFT Datasets**](reference/sql-query-tables/polygon/nft-tables.md)

| NFTs                                    | `polygon.nfts`                  |                                        |
| --------------------------------------- | ------------------------------- | -------------------------------------- |
| NFT Contracts                           | `polygon.nft_contracts`         |                                        |
| NFT Transfers (with optional hold time) | `polygon.nft_transfers`         | `polygon.recent_nft_transfers`         |
| NFT Owners                              | `polygon.nft_owners`            |                                        |
| NFT Airdrop Transfers                   | `polygon.nft_airdrop_transfers` | `polygon.recent_nft_airdrop_transfers` |

[**Bitcoin datasets**](reference/sql-query-tables/bitcoin.md)

| Blocks              | `btc.blocks`              | `btc.recent_blocks`              |
| ------------------- | ------------------------- | -------------------------------- |
| Transactions        | `btc.transactions`        | `btc.recent_transactions`        |
| Transaction Inputs  | `btc.transaction_inputs`  | `btc.recent_transaction_inputs`  |
| Transaction Outputs | `btc.transaction_outputs` | `btc.recent_transaction_outputs` |

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

#### [Chainlink datasets](reference/sql-query-tables/sql-query-tables/chainlink-tables/)

|                     |                        |                               |
| ------------------- | ---------------------- | ----------------------------- |
| Prices (historical) | `eth.chainlink.prices` | `eth.chainlink.recent_prices` |

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

### JSON RPC Methods

* See [JSON RPC Methods](datasets.md#time-series-datasets-1)

