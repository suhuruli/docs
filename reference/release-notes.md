---
description: Spice.xyz Release notes
---

# Release notes

### April 2023

This month we added new datasets including Chainlink prices data feeds, Aave v2 contract data, Ethereum Shanghai/Capella beacon and withdrawals data, and we now fully index the Goerli testnet. We also released the Goerli Beacon and Ethereum Beacon APIs. \
\
**Chainlink Data Feeds:** You can now leverage oracles for various data feed on the Chainlink network by querying prices specific tables including `eth.chainlink.prices` and `eth.chainlink.recent_prices`.

This includes accessing the latest, minute-precision data on `transaction_hash`, `oracle_address`, `block_timestamp`, price of the asset in WEI, `asset_address` and more. The columns and their schema available for each table can be viewed with the describe \<table> command:

<pre class="language-sql"><code class="lang-sql"><strong>/* Show the columns available */
</strong>DESCRIBE eth.chainlink.prices;
</code></pre>

With this release, we now support data feeds for Curve, Balancer, Aave, Yearn, DAI, Tether USD and 30 other top assets. See the full list of supported data feeds [here](https://docs.spice.xyz/reference/sql-query-tables/sql-query-tables/chainlink-tables/prices-tables).&#x20;

\
**Aave V2 Dataset:** In addition to the Aave token prices data feed on the Chainlink network, we have released indexed [Aave V2](sql-query-tables/sql-query-tables/aave-v2-tables.md) data for loans, collaterals and prices. You can query for the latest updates to Aave loans and collateral by querying `eth.aave_v2.loan_updates` and `eth.aave_v2.collateral_updates`.&#x20;

<figure><img src="../.gitbook/assets/Screen Shot 2023-05-09 at 9.49.27 AM.png" alt=""><figcaption><p>Latest view of all Aave V2 loans query, sample output</p></figcaption></figure>

\
**Ethereum Shanghai Upgrade and Withdrawals Datasets:** Spice added support for the [Ethereum Shanghai/Capella upgrade](https://blog.ethereum.org/2023/03/28/shapella-mainnet-announcement) which was completed on April 12, 2023, 10:27:35pm UTC at epoch 194048.

The completion of Ethereum's Shanghai hard fork, also known as "Shapella," has authorized the withdrawal of funds for individuals who have "staked" their ETH to validate and secure blockchain transactions.

As part of this upgrade, we have also released the `eth.withdrawals` dataset to capture new withdrawals. For example, you can now query to get ETH withdrawn:

```sql
with eth_withdrawn as (
  select eth.withdrawals.block_number, SUM(amount) as amount_gwei
  from eth.withdrawals
  group by eth.withdrawals.block_number
  order by block_number asc)

select AVG(amount_gwei / 1e9) as amount_eth
from eth_withdrawn
```

<figure><img src="../.gitbook/assets/Screen Shot 2023-05-10 at 10.20.00 PM.png" alt=""><figcaption><p>Get ETH withdrawn after the Ethereum Shanghai upgrade, sample output</p></figcaption></figure>

Explore detailed sample SQL queries for [DEX](example-dex-queries/), [Cross-Chain](example-cross-chain-queries.md), [Ethereum](example-ethereum-sql-queries/), [Beacon](example-ethereum-beacon-sql-queries/), and [Bitcoin](example-bitcoin-queries/) in the Spice Docs.\


**Goerli Testnet Datasets:** Real-time and historical Goerli chain data is now supported on [Spice.xyz](https://spice.xyz). Users can query and access Goerli base type tables, Goerli token specific tables, and Goerli Beacon Chain specific tables. &#x20;

We’re excited help web3 developers test their applications before launching them on the Ethereum Mainnet.&#x20;

You can start by querying `goerli.traces`, `goerli.blocks`, and check out the full token tables list [here](https://docs.spice.xyz/reference/sql-query-tables/goerli/token-tables) or by querying:&#x20;

```sql
SHOW TABLES IN goerli
```

All Goerli Beacon Chain specific tables are listed [here](https://docs.spice.xyz/reference/sql-query-tables/goerli/beacon-chain-tables) or by querying:&#x20;

```sql
SHOW TABLES IN goerli.beacon
```

For example, you can query from `goerli.beacon.validators` to retrieve recently updated validators, with their balance and status:

<figure><img src="../.gitbook/assets/Screen Shot 2023-05-09 at 8.33.15 PM.png" alt=""><figcaption><p>Recently updated validators, with their balance and status by querying from <code>goerli.beacon.validators</code>, sample output</p></figcaption></figure>

**Goerli Beacon API:** You can also easily retrieve requests like "[get validator balances from state](https://docs.spice.xyz/api/goerli/beacon-http-api)" using the **`https://data.spiceai.io/goerli/beacon`** API, which is compatible with the read-only GET requests from the [Beacon Node API specification](https://ethereum.github.io/beacon-APIs/).

All [Goerli testnet data APIs](../api/goerli/) are available at **/goerli/v0.1** including the following:

* [JSON RPC Methods](../api/goerli/json-rpc-methods.md)
* [Beacon HTTP API](../api/goerli/beacon-http-api.md)
* [Blocks](../api/goerli/blocks.md)
* [Contracts](../api/goerli/contracts.md)
* [Gas Fees](../api/goerli/gas-fees.md)

**Ethereum Beacon API:** The [Ethereum API](../api/ethereum/) is now updated to support Beacon requests via the **`https://data.spiceai.io/eth/beacon`** API. This is compatible with the read-only GET requests from the [Beacon Node API specification](https://ethereum.github.io/beacon-APIs/).&#x20;

See the full list of Beacon API requests [here](https://docs.spice.xyz/api/ethereum/beacon-http-api).&#x20;



**New In this Release**

* \[Goerli] added `goerli.blocks`, `goerli.recent_blocks`&#x20;
* \[Goerli] added `goerli.transactions`, `goerli.recent_transactions`&#x20;
* \[Goerli] added `goerli.logs`, `goerli.recent_logs`&#x20;
* \[Goerli] added `goerli.traces`, `goerli.recent_traces`&#x20;
* \[Goerli] added `goerli.withdrawals`, `goerli.recent_withdrawals`&#x20;
* \[Goerli] added `goerli.contracts`&#x20;
* \[Goerli] added `goerli.tokens`
* \[Goerli] added `goerli.token_transfers`
* \[Goerli] added `goerli.tokens_erc20`
* \[Goerli] added `goerli.token_transfers_erc20`
* \[Goerli] added `goerli.tokens_erc721`
* \[Goerli] added `goerli.token_transfers_erc721`
* \[Goerli] added `goerli.tokens_erc1155`
* \[Goerli] added `goerli.token_transfers_erc1155`
* \[Goerli] added `goerli.token_mints`
* \[Goerli] added `goerli.recent_token_mints`
* \[Goerli] added `goerli.beacon.slots`, `goerli.beacon.recent_slots`
* \[Goerli] added `goerli.beacon.voluntary_exits`, `goerli.beacon.recent_voluntary_exits`
* \[Goerli] added `goerli.beacon.attestations`, `goerli.beacon.recent_attestations`
* \[Goerli] added `goerli.beacon.attester_slashings`, `goerli.beacon.recent_attester_slashings`
* \[Goerli] added `goerli.beacon.deposits`, `goerli.beacon.recent_deposits`
* \[Goerli] added `goerli.beacon.proposer_slashings`, `goerli.beacon.recent_proposer_slashings`
* \[Goerli] added `goerli.beacon.bls_to_execution_changes`, `goerli.beacon.recent_bls_to_execution_changes`
* \[Goerli] added `goerli.beacon.withdrawals`, `goerli.beacon.recent_withdrawals`
* \[Beacon] added [Goerli Beacon HTTP API](https://docs.spice.xyz/api/goerli/beacon-http-api)
* \[Beacon] added [Ethereum Beacon HTTP API ](https://docs.spice.xyz/api/ethereum/beacon-http-api)
* \[Aave V2] added `eth.aave_v2.loan_updates`, `eth.aave_v2.loans`
* \[Aave V2] added `eth.aave_v2.collateral_updates`, `eth.aave_v2.collateral`
* \[Chainlink] added `eth.chainlink.prices`, `eth.chainlink.recent_prices`
* \[Chainlink] added [price feed support](sql-query-tables/sql-query-tables/chainlink-tables/) for the following assets:
  * USD Coin (USDC)&#x20;
  * 1INCH Token (1INCH)&#x20;
  * Yearn.finance (YFI)&#x20;
  * Dai Stablecoin (DAI)&#x20;
  * DefiPulse Index (DPI)&#x20;
  * UST (UST)&#x20;
  * Decentraland MANA (MANA)&#x20;
  * Liquid staked Ether 2.0 (stETH)&#x20;
  * ChainLink Token (LINK)&#x20;
  * Balancer (BAL)&#x20;
  * Enjin Coin (ENJ)&#x20;
  * Tether USD (USDT)&#x20;
  * Wrapped BTC (WBTC)&#x20;
  * Maker (MKR)&#x20;
  * Convex Token (CVX)&#x20;
  * Fei USD (FEI)&#x20;
  * Uniswap (UNI)&#x20;
  * Pax Dollar (USDP)&#x20;
  * Kyber Network Crystal (KNC)&#x20;
  * Aave Token (AAVE)&#x20;
  * 0x Protocol Token (ZRX)&#x20;
  * Binance USD (BUSD)&#x20;
  * SushiBar (xSUSHI)&#x20;
  * Republic Token (REN)&#x20;
  * renFIL (renFIL)&#x20;
  * Basic Attention Token (BAT)&#x20;
  * Synthetix Network Token (SNX)&#x20;
  * Ampleforth (AMPL)&#x20;
  * Frax (FRAX)&#x20;
  * Rai Reflex Index (RAI)&#x20;
  * Synth sUSD (sUSD)&#x20;
  * TrueUSD (TUSD) \


#### Changes

* \[Portal] Improved performance of portal pages
* \[Performance] Improved query performance, data redundancy, and scale by migrating to new infrastructure

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### March 2023

If you are waitlisted, you can now instantly enable your account by signing up for a preview plan at 50% off. This month's release also includes support for the Ethereum Beacon chain dataset and improved monitoring with request logs.

**Self-Service Activation from Waitlist:** as a waitlisted customer, you can now enable your account instantly without manual Spice AI approval when you sign up for a Pro for Teams or Lite Plan. Begin a 7-day trial of the Pro for Team plan, then monthly subscription of $1,245 at 50% off (normally $2,490). It comes with early access (off the waitlist), dedicated support on Discord, and a bi-weekly sync with the Spice AI engineering team.

**Improved monitoring:** you can now track requests, their status code, and duration to Spice, in addition to the existing usage monitoring metrics dashboard. Start by going to your app, under the Monitor sidebar, select API Requests. You can then toggle between Metrics and Logs views. Within Logs, you can select to retrieve API requests from the past 1 hour, 8 hours, 24 hours, and up to the past 3 days.

<figure><img src="../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

**Ethereum Beacon Chain Dataset (Preview):** The Ethereum beacon chain is the central coordination and consensus layer for the Ethereum 2.0 upgrade, which aims to improve scalability, security, and sustainability. Now you can query and access beacon chain dataset with `eth.beacon`, `eth.beacon.validators`, `eth.beacon.withdrawals` and more.

You can also reference the full query list via [Ethereum Beacon tables](https://docs.spice.xyz/reference/sql-query-tables/sql-query-tables/beacon-chain-tables) or by directly querying the following in the application:

```sql
SHOW TABLES IN eth.beacon
```

[Example SQL queries](https://docs.spice.xyz/reference/example-ethereum-beacon-sql-queries) include slots, attestations, validators, deposits, voluntary exits, attester slashings and more, all retrievable within a few seconds.&#x20;

Sample Queries

1.  ENS Domain Names that map to a validator\


    <figure><img src="../.gitbook/assets/Screen Shot 2023-04-24 at 10.59.20 PM (3).png" alt=""><figcaption></figcaption></figure>
2.  Number of Weekly Attester Slashings \


    <figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
3.  Top 10 most frequent block proposers\


    <figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

By leveraging beacon chain capabilities, developers can create scalable decentralized applications that can handle a large volume of transactions, while also participating in network governance and incentivization through its Proof of Stake consensus mechanism. You can learn more about the chain [here](https://www.alchemy.com/overviews/what-is-the-ethereum-beacon-chain).&#x20;

#### New In this Release

* \[Portal] Added Self-Service account activation
* \[Beacon] Added Ethereum beacon chain dataset `eth.beacon`
* Beacon] Added Ethereum beacon chain dataset `eth.validators`
* \[Beacon] Added Ethereum beacon chain datasets `eth.beacon.slots`, `eth.beacon.recent_slots`
* \[Beacon] Added Ethereum beacon chain datasets `eth.beacon.attestations`, `eth.beacon.recent_attestations`
* \[Beacon] Added Ethereum beacon chain datasets `eth.beacon.deposits`, `eth.beacon.recent_deposits`
* \[Beacon] Added Ethereum beacon chain datasets `eth.beacon.voluntary_exits`, `eth.beacon.recent_voluntary_exits`
* \[Beacon] Added Ethereum beacon chain datasets `eth.beacon.attester_slashings`, `eth.beacon.recent_attester_slashings`
* \[Beacon] Added Ethereum beacon chain datasets `eth.beacon.proposer_slashings`, `eth.beacon.recent_proposer_slashings`
* \[Beacon] Added Ethereum beacon chain datasets `eth.beacon.bls_to_execution_changes`, `eth.beacon.recent_bls_to_execution_changes`
* \[Beacon] Added Ethereum beacon chain datasets `eth.beacon.withdrawals`, `eth.beacon.recent_withdrawals`

#### Changes

* \[Portal] Improved performance of portal pages

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### February 2023

Spice released the NFT dataset with Metadata in preview, along with the Historic Prices API in preview, and the v0.3 update to the Node.js SDK [spice.js](https://www.npmjs.com/package/@spiceai/spice).&#x20;

**Historic Prices API (Preview):** In addition to accessing the [Spot Prices](https://docs.spice.xyz/api/prices#spot-prices) of popular token/currency pairs on top exchanges, users can now access the **`/v0.1/prices/[pair]`** API, which returns historical prices of the specified token/currency pair. You can refine your search by defining parameters like `start` and `end`, which will return all prices between the two timestamps at a provided `granularity`.

Please contact us if you would like to access the API. \
\
**NFT Dataset with Metadata (Preview):** You can now query and leverage fungible and non-fungible token contracts under `eth.tokens` as well as isolated NFT specific per token information under `eth.nfts`. These are made available also with name and symbol for ERC721 tokens. See the full list of [NFT tables](https://docs.spice.xyz/reference/sql-query-tables/sql-query-tables/nft-tables) and [Token tables](https://docs.spice.xyz/reference/sql-query-tables/sql-query-tables/token-tables).&#x20;

**Node.js SDK v0.3:** adds support for improved [Prices APIs](https://docs.spice.xyz/api/prices) supporting spot/latest and historical prices for pair across Coinbase, Gemini, and tracked by Coinmarket Cap. This upgrade ensures the SDK remains the easiest way to use and query [Spice.xyz](https://spice.xyz) with Node.js.

It uses [Apache Apache Flight](https://arrow.apache.org/docs/format/Flight.html) to efficiently stream data to the client and [Apache Arrow](https://arrow.apache.org/) Records as data frames which are then easily converted to JavaScript objects/arrays or JSON.

New functions available on the client are:

* `getPrice()`
* `getPrices()`

You'll need [Node.js 16+](https://nodejs.org/) to get started. See the step-by-step installation guide [here](https://docs.spice.xyz/sdks/node.js-sdk).&#x20;

#### New In this Release

* \[API] Added [Historic Prices API in Preview](https://docs.spice.xyz/api/prices#historical-prices-preview)
* \[Node.js SDK] [v0.3 release](https://docs.spice.xyz/sdks/node.js-sdk) of Node.js SDK [spice.js](https://www.npmjs.com/package/@spiceai/spice)
* \[NFT and Metadata] [NFT](https://docs.spice.xyz/reference/sql-query-tables/sql-query-tables/nft-tables) and [Token](https://docs.spice.xyz/reference/sql-query-tables/sql-query-tables/token-tables) datasets in preview&#x20;

#### Changes

* \[Performance] Improved query performance and scale
* \[Portal] Improved performance of portal pages
* \[Node.js SDK] Add `getPrice` and `getPrices` API&#x20;

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)





### January 2023

Sharing a packed release this month focused on a new dataset, org management, two developer querying tools, and two SDKs.

**Ethereum Name Service (ENS) Events:** now out of preview, it's available by querying `ens.domains`, which is updated in real-time to have the latest `eth_address`whenever a transfer or name-registered event happens. Both `eth.ens` and other on-demand events indexed under the `eth.ens` prefix such as `eth.ens_event_nameregistered` are updated in real time with the same high-performance standards of published Spice datasets. See the tables [here](https://docs.spice.xyz/reference/sql-query-tables/sql-query-tables/token-tables-1).

**Organization Management:** existing users can start exploring org support and management for users, apps, and datasets by [authorizing Spice with read-only access](https://docs.spice.xyz/get-started/portal-login) when logging into the [Spice.xyz](http://spice.xyz/) portal. This will also act as a parent container for future concepts including apps, users, teams, datasets, and metrics for streamlined management and navigation within [spice.xyz](http://spice.xyz/).

The big game changers this month are [Async Query](https://docs.spice.xyz/api/sql-query-api/http-api-1) and [Flow AI Query Auto-Complete (in preview)](https://medium.com/spice-ai/introducing-spice-ai-flow-8bcfc5cc2294) — which supercharge the developer experience.

**Async Query API:** you can post a JSON payload specifying list of query completion, and  `notifications` results can be fetched asynchronously once the query has completed. Choose function client apps such as AWS Lambda to async query Spice.xyz and receive result notifications by webhook. Results are accessible up to 20 minutes after they are posted.

**Flow (AI SQL Query Auto-Complete):** you can now query with plain text, hit enter, and watch as Flow autocompletes the request with the corresponding SQL lines in your [spice.xyz](http://spice.xyz/) query editor. Hit tab to accept the AI-generated completion, then accept, reject, or edit before run the query.

We've also released the new [gospice Golang SDK](https://docs.spice.xyz/sdks/go) and added improvements to our [Python SDK](https://docs.spice.xyz/sdks/python-sdk) including timeout support.

**Go SDK:** gospice is the easiest way to query [Spice.xyz](https://spice.xyz/) from Go. It uses [Apache Apache Flight](https://arrow.apache.org/docs/format/Flight.html) to efficiently stream data to the client and [Apache Arrow](https://arrow.apache.org/) Records as data frames.\
GoDocs available at [pkg.go.dev/github.com/spiceai/gospice](https://pkg.go.dev/github.com/spiceai/gospice).

We continue to make performance improvements for faster, more reliable queries and also recently launched our much anticipated Polygon Support, which you can read more about [here](https://blog.spice.ai/build-multi-chain-with-spice-ai-now-with-polygon-support-9db156f36d80).

Read the announcement post at [blog.spice.ai](https://blog.spice.ai/spice-xyz-january-update-whats-new-dd50f2233f47)

#### New In this Release

* \[Portal] Added [organizations support and management](https://docs.spice.xyz/portal/organizations#organization-management)
* \[Portal] Added [AI-driven SQL Query Auto-Complete](https://docs.spice.xyz/portal/query-editor#ai-sql-completion-preview)
* \[API] Added [Async Query API](https://docs.spice.xyz/api/sql-query-api/http-api-1)
* \[ENS] General availability of [ENS data](https://docs.spice.xyz/reference/sql-query-tables/sql-query-tables/token-tables-1) out of preview
* \[Go SDK] Initial release of [Golang SDK](https://docs.spice.xyz/sdks/go)

#### Changes

* \[Performance] Improved query performance and scale
* \[Portal] Improved performance of portal pages
* \[Polygon] Added [WebSocket support](https://docs.spice.xyz/faq#do-you-support-websockets-or-other-streaming) for Polygon
* \[Python SDK] Added support for Python 3.11
* \[Python SDK] Added back support for Python 3.7
* \[Python SDK] Added query timeout support
* \[Python SDK] Upgraded to pyarrow 10.0.1
* \[Node.js SDK] Added Async query support
* \[Node.js SDK] Upgraded to arrow 10.0.1

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### December 2022

Spice supports querying [Polygon data](sql-query-tables/polygon/) in addition to the existing [Ethereum](sql-query-tables/sql-query-tables/) and [BItcoin](sql-query-tables/bitcoin.md) datasets.

Read more on the [Spice AI Blog](https://blog.spice.ai/build-multi-chain-with-spice-ai-now-with-polygon-support-9db156f36d80).

**Changes**

* Support for fundamental Polygon datasets and NFT specific tables&#x20;
  * `polygon.blocks` / `polygon.recent_blocks`
  * `polygon.transactions` / `polygon.recent_transactions`
  * `polygon.nft_transfers` /`polygon.recent_nft_transfers`&#x20;
  * `polygon.nft_airdrop_transfers` / `polygon.recent_nft_airdrop_transfers`
  * `polygon.nft_owners`
* View the columns and their schema available for each table with the `describe <table>` command&#x20;

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### November 2022

**DEX Liquidity & Events Dataset**

Spice now features DEX Liquidity and Events Dataset where users can access indexed liquidity data from UniSwap \[[V2](sql-query-tables/ethereum/uniswap-v2-tables.md), [V3](sql-query-tables/ethereum/uniswap-v3-tables.md)] and [SushiSwap](sql-query-tables/ethereum/sushiswap-tables.md) liquidity pools, _within seconds_.&#x20;

Data is available both historically and in real time, providing unparalleled visibility on DEX liquidity pools.

**ENS (Preview)**\
You can now preview the new dataset for [Ethereum Name Service events](sql-query-tables/ethereum/token-tables-1.md), available by querying `eth.ens`. Within the dataset, you’ll find that each ENS event will have its own table as immutable data.

This also includes the new `ens.domains` dataset, which is updated in real-time to have the latest `eth_address` whenever a transfer or name-registered event happens

Read more on the [Spice AI blog](https://blog.spice.ai/whats-new-b7f637897df8).

**Changes**

* [Prices dataset](sql-query-tables/prices/) now out of preview
* Added export to CSV results format in addition to existing formats [JSON](../api/ethereum/json-rpc-methods.md) and [Apache Arrow](../api/sql-query-api/apache-arrow-flight-api.md), for easy use with apps, ML, or libraries like NumPy and Pandas
* Added performance improvements for faster queries across existing datasets including `eth.traces`&#x20;

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### October 2022

Spice now has [prices dataset](sql-query-tables/prices/) in preview.&#x20;

* Query historical High-Low-Open-Close (HILO) prices to minute precision
* Join with other real-time and historical web3 data to do calculations and conversions back to USD
* Initial data sources include Gemini, Coinbase, SushiSwap, and UniSwap (a mix of CEX, DEX, and third parties)

Read more on the [Spice AI blog](https://blog.spice.ai/whats-new-b7f637897df8).

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### September 2022

**Ethereum Traces Dataset**

Spice launches the `eth.traces` dataset for both Ethereum and Polygon. The Ethereum internal transactions are available for query at `eth.traces` and are updated in real-time.



**Polygon Support (Preview)**

Spice launches and tests [Polygon support](sql-query-tables/polygon/).

**Changes**

* completed real-time indexing and parquet writing for Polygon
* incorporated asynchronous process block notifications to enable Polygon support
* added improvements on data integrity and bug fixes
* added transaction\_hash and block\_timestamp to `eth.nft_owners`

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### August 2022

Key infrastructure improvements were made for Spice's query performance, security, and data availability.

**Changes**

* Improved performance for node configuration
* Upgrade dremio infrastructure
* Expanded node memory for broader availability

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### July 2022

Spice supports querying [Bitcoin data](sql-query-tables/bitcoin.md) in addition to the existing [Ethereum datasets](sql-query-tables/sql-query-tables/).

Read more on the [Spice AI blog](https://medium.com/spice-ai/).

**Changes**

* Support for fundamental Bitcoin datasets
  * `btc.blocks` / `btc.recent_blocks`
  * `btc.transactions` / `btc.recent_transactions`
  * `btc.transaction_inputs` / `btc.recent_transaction_inputs`
  * `btc.transaction_outputs` / `btc.recent_transaction_outputs`
* [example-bitcoin-queries](example-bitcoin-queries/ "mention") for querying Bitcoin data.

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### June 2022

This update includes a new [Javascript/Typescript SDK](../sdks/node.js-sdk/) for Node.js, an improved [Python SDK](../sdks/python-sdk.md), and performance improvements for Ethereum tokens and NFT datasets.

[Ethereum Name Service (ENS)](sql-query-tables/ethereum/token-tables-1.md) support is also available in beta with the new `ens.domains` dataset.

Read more on the [Spice AI blog](https://medium.com/spice-ai/spice-xyz-june-update-f74d60faff61).

**Changes**

* New [Node.js SDK](../sdks/node.js-sdk/)
* Improved [Python SDK](../sdks/python-sdk.md)
* ENS support in beta
  * `ens.domains`
* Improved performance for `eth.tokens_` and `eth.nft_` prefixed tables

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### May 2022

Spice now has some of the best automated token standard detection for erc20, erc721, and erc1155 tokens available. Tokens are detected by their signatures and as they emit events over time, so Spice provides a probability of standards compliance to each contract. Along with this support are now token-specific tables like `eth.tokens_erc1155` and `eth.token_transfers_erc20`. See the entire list [Tokens Tables](sql-query-tables/sql-query-tables/token-tables.md).

Performance is now even better, especially for larger queries, and for results over the HTTP API. We still recommend the [Apache Arrow Flight API](../api/sql-query-api/apache-arrow-flight-api.md) that's easily accessible via the [Python SDK](../sdks/python-sdk.md) for production use though.

WebSocket support is now available in private preview to Design Partners - get in touch if you are interested in custom limits, early access features, and dedicated support.

#### Changes

* Improved Ethereum standard detection for erc20, erc721, and erc115 tokens
* Added new token specific tables
  * `eth.tokens_erc20`
  * `eth.tokens_erc721`
  * `eth.tokens_erc1155`
  * `eth.token_transfers_erc20`
  * `eth.token_transfers_erc721`
  * `eth.token_transfers_erc1155`
* Added new columns to `eth.token_transfers` table
  * `token_standard`
  * `token_id`
* Added new columns to `eth.contracts` table
  * `erc20_confidence`
  * `erc721_confidence`
  * `erc1155_confidence`
  * `is_erc1155`
* `eth.nft_` tables now include erc1155 tokens

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### Apr 2022

Spice is now hosted at [**spice.xyz**](https://spice.xyz)! And with this release Spice is now **100% data complete**! We also have new **combined documentation** at [docs.spice.xyz](https://docs.spice.xyz), new **NFT specific tables** like `nft_transfers` and `nft_airdrop_transfers`, significantly **improved erc721 detection**, and **higher data integrity**.

#### Changes

* Now hosted at [spice.xyz](https://spice.xyz)
* Now 100% data complete on core Ethereum tables
* Refreshed documentation site at [docs.spice.xyz](https://docs.spice.xyz)
* Added `input` field to the `transactions` table
* Added `data`, `topics`, `block_timestamp` fields to the `logs` table
* Added `block_timestamp` and `block_hash` to the `token_transfers` table

#### Breaking Changes

* The receipts table fields have been moved to the transactions table with prefix receipt\_. The told receipts table has been removed.
* `receipts.cumulative_gas_used` → `transactions.receipt_cumulative_gas_used`
* `receipts.gas_used` → `transactions.receipt_gas_used`
* `receipts.contract_address` → `transactions.receipt_contract_address`
* `receipts.root` → `transactions.receipt_root`
* `receipts.effective_gas_price` → `transactions.receipt_effective_gas_price`

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### Mar 2022

More improvements to performance and data completeness. Now 99.99% complete for Ethereum base types.

Significantly improved erc721 detection and now include new `nft` specific tables including `eth.nft_contracts`, `eth.nft_transfers` and `eth.nft_airdrop_transfers`.

#### Changes

* Improved erc721 detection, now with 28,000+ erc721 rows
* Adds `eth.nft_contracts` table
* Adds `eth.nft_transfers` table
* Adds `eth.nft_airdrop_transfers` table
* Adds `eth.recent_blocks` table which holds the latest 100 blocks
* More improvements to query performance
* Now at 99.99% data complete

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### Feb 2022

Significant upgrades in performance and data completeness. Adds the ability to query Ethereum, Sushiswap, and Uniswap data with SQL. Adds an Apache Flight endpoint.

#### Changes

* Adds SQL query
* Adds Sushiswap, Uniswap-V2, and Uniswap-V3 liquidity data
* Adds Apache Flight endpoint
* Adds management portal
* Significantly improved performance with the ability to query across real-time and historical data

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### Jan 2022

Initial release of the Spice beta!

#### Changes

* The Initial release of the Spice Private Beta!
* Adds `/eth/v0.1/gasfees` API.
* Adds `/eth/v0.1/contracts` API.
* Adds `/v0.1/prices` API.
