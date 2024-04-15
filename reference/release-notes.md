---
description: Monthly release notes for the Spice.ai Cloud Platform
---

# Release Notes

### March 2024

**Ethereum Goerli nodes were shutdown on Friday March 22 at 5pm PST.**

The Ethereum Foundation planned to stop supporting Goerli [one month after Dencun](https://nam12.safelinks.protection.outlook.com/?url=https%3A%2F%2Fspice.us5.list-manage.com%2Ftrack%2Fclick%3Fu%3De853435dd452a4d343ea1133d%26id%3D1f0eddc002%26e%3D9d81a8fb5f\&data=05%7C02%7Cluke%40spice.ai%7C2ecaa574022c4aac7f8c08dc4833dd51%7C925431232b6a4eec9b6f595720cd1c8f%7C0%7C0%7C638464634819771165%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C\&sdata=6xvJI%2Fdn210TQ7ejvHXrdNTQCH7wkUF2ARQ8JHXCJ1c%3D\&reserved=0) was activated on Ethereum mainnet, which would be April 13th, however nearly all Goerli Validators were already shut down, effectively shutting the network down prematurely. Spice AI is shut down nodes early  aligned to other providers decisions to also shut down, such as [Alchemy](https://nam12.safelinks.protection.outlook.com/?url=https%3A%2F%2Fspice.us5.list-manage.com%2Ftrack%2Fclick%3Fu%3De853435dd452a4d343ea1133d%26id%3D351e541bfd%26e%3D9d81a8fb5f\&data=05%7C02%7Cluke%40spice.ai%7C2ecaa574022c4aac7f8c08dc4833dd51%7C925431232b6a4eec9b6f595720cd1c8f%7C0%7C0%7C638464634819780937%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C\&sdata=HAX45r3B5W95bt3JRpQvgoGN1Q7brf4yFHNtdYk4%2BKg%3D\&reserved=0).

After the shutdown, JSON RPC and Beacon requests to **/goerli** returned 404 Not Found and Goerli SQL datasets, while still available for query, are no longer being updated, including Firecache datasets.

[Goerli SQL Tables](https://nam12.safelinks.protection.outlook.com/?url=https%3A%2F%2Fspice.us5.list-manage.com%2Ftrack%2Fclick%3Fu%3De853435dd452a4d343ea1133d%26id%3D8eb3381cbc%26e%3D9d81a8fb5f\&data=05%7C02%7Cluke%40spice.ai%7C2ecaa574022c4aac7f8c08dc4833dd51%7C925431232b6a4eec9b6f595720cd1c8f%7C0%7C0%7C638464634819763981%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C\&sdata=I%2BdPMW%2FBgLUJXMio7efzCxu3l2R1ju9RLE%2FcvxK0w54%3D\&reserved=0) will remain available for historical query purposes.

The [Ethereum](sql-query-tables/ethereum/) and [Beacon](sql-query-tables/ethereum/beacon-chain-tables/) datasets now include fields from the Cancun and Dencun network upgrade.

**Changes**

1. \[Rust SDK] Released v1.0.3
2. \[API] Removed Goerli JSON-RPC API
3. \[Data] SQL datasets for Ethereum and Beacon chains now include Cancun and Dencun fields.

### February 2024

The February release focused on stability and performance improvements.

**Changes**

1. \[Platform] Performance, reliability, and security improvements.

### January 2024

The January release added support for the Ethereum [Holesky](https://github.com/eth-clients/holesky) testnet in preview. Holesky data can be explored in the portal Playground, queried by [SQL](sql-query-tables/holesky/) and Firecache, and made available to applications by JSON-RPC [API](../api/holesky/). &#x20;

<figure><img src="../.gitbook/assets/image (37).png" alt=""><figcaption><p>Holesky Testnet APIs and datasets available in preview</p></figcaption></figure>

**New in this release**

1. \[Platform] Added Ethereum [Holesky](sql-query-tables/holesky/) testnet data and API's.
2. \[Platform] Achieved [SOC 2 Type II compliance](../security/security.md).

**Changes**

1. \[Platform] Performance, reliability, and security improvements.
2. \[Node JS SDK] [Released v1.0.2](https://github.com/spiceai/spice.js/releases/tag/v1.0.2).

### December 2023

The December release focused on stability and performance improvements.

**Changes**

1. \[Platform] Performance, reliability, and security improvements.

### November 2023

The November release focused on [External Data Sources](../building-blocks/external-data-sources.md) and overall performance improvements following the [General Availability (GA)](https://blog.spice.ai/spice-ai-is-generally-available-d76c4289960c) release in October.

You can now connect external data sources like PostgreSQL and MySQL to Spice.ai, which are then available to query with SQL including joining with any other Spice.ai dataset in the Spice.ai platform.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>New Data Source dialog for connecting external data sources.</p></figcaption></figure>

Navigation is also easier with the addition of the Command Bar. Simply use **Cmd+K** on Mac or **Windows+K** in Windows to quickly navigate the portal by keyboard! Give it a try!

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>The new navigation command bar.</p></figcaption></figure>

**New In this Release**

1. \[Portal] Added PostgreSQL and MySQL external data sources. See the [docs](../building-blocks/external-data-sources.md) for details.
2. \[Portal] Added Dark Mode! Configure via [Profile Settings](../portal/profile-settings.md#dark-mode).
3. \[Portal] Added Command Bar navigation.
4. \[Data] Added [`eth.wallet_lst_balances`](sql-query-tables/ethereum/wallet-balances/eth.wallet\_lst\_balances.md) including rETH, stETH, and cbETH LSTs.
5. \[Firecache] Upgraded to DuckDB 0.92.
6. \[Platform] Performance, reliability, and security improvements.
7. \[Go SDK] Released v3.0.0, [learn more](https://github.com/spiceai/gospice/releases/tag/v3.0.0).

### October 2023

Spice.ai is now generally available! [Read the announcement](https://blog.spice.ai/spice-ai-is-generally-available-d76c4289960c).

General Availability launches a brand-new collaborative developer experience, v1 APIs and SDKs, over [100 open-source community](https://github.com/spiceai/datasets) and [EigenLayer](sql-query-tables/ethereum/eigenlayer-tables/) datasets, and a removal of the waitlist. Any developer can now sign-up and use Spice.ai with one of the new [pricing plans](../getting-started/pricing/), including the $99 developer plan and the complementary [Community Edition](../getting-started/pricing/community-edition.md).

**New In this Release**

1. \[HTTP API] Add v1 API:
   1. [SQL Query API ](../api/sql-query/http-api.md)
   2. [Prices API](../api/prices-api.md)
   3. [Gas Fees API](../api/ethereum/gas-fees.md)
   4. [Predictions API](../api/predictions/)
2. \[Portal] New Portal and developer experience, without waitlist limitations.
3. \[Portal] New pricing plans are available, [learn more](https://docs.spice.ai/getting-started/pricing).
4. \[Portal] Datasets and Views generally available, [learn more](release-notes.md#datasets-and-views).
5. \[Firecache] Upgraded to DuckDB 0.91.
6. \[Functions] Upgraded to DuckDB 0.91.
7. \[Ethereum] Added support for `eth_maxPriorityFeePerGas` and `trace_filter` to JSON RPC API.
8. \[Ethereum] Expanded Ethereum client diversity by adding [Reth](https://github.com/paradigmxyz/reth) support.
9. \[Ethereum] Expanded Polygon client diversity by adding Erigon support.
10. \[Python SDK] v1.0.0 released, [learn more](https://github.com/spiceai/spicepy/releases/tag/v1.0.0).
11. \[Go SDK] v3.0.0 released, [learn more](https://github.com/spiceai/gospice/releases/tag/v3.0.0).
12. \[Node.js SDK] v1.0.0 released, [learn more](https://github.com/spiceai/spice.js/releases).
13. \[Rust SDK] v1.0.1 released, [learn more](https://github.com/spiceai/spice-rs/releases/tag/v1.0.1).

### September 2023

In the September release, Crypto/Token Prices data has been significantly expanded and improved upon.

Historical and latest prices are available via [REST API](../api/prices-api.md) and [SQL Query](broken-reference).

The number of token pairs supported by the REST API has greatly increased. In addition, if a pair does not have swap data, the platform will attempt to calculate a synthetic price for the pair, routed via swaps across different exchanges. For example, if a price for the pair BAO-AUD does not exist, but the pairs BAO-USDT and USDT-AUD do, then the API will calculate the routed price across the two swaps to determine a synthetic price, which will be returned in the payload as the `spiceai` price. The API will use data cross both centralized and decentralized exchanges. This enables pricing data where it was not possible before.

Additional tables have been added for token prices and assets.

* [prices.assets](broken-reference) list all assets tracked and available via SQL Query. 8,856 assets are currently available.
* [prices.all\_pairs](broken-reference) list all the token pairs with prices available via SQL Query. 3,342 pairs are currently available.

In addition to the existing [prices.\[tokenA-tokenB\]](sql-query-tables/ethereum/chainlink-tables/prices-tables/) a table of prices for each token pair.

Note: In both cases, the list is a subset of what is available via the REST API.

**New In this Release**

1. \[SQL Query] Added `prices.assets` table.
2. \[SQL Query] Added `prices.all_pairs` table.
3. \[Prices API] Added swap routed token pricing.
4. \[Prices API] Enhanced coverage of token pairs.
5. \[Portal] Bugfixes and minor improvements to the UI.

### August 2023

The August release expands the functionality of [Spice Functions](broken-reference) (beta) and [Datasets and Views](../building-blocks/datasets-and-views.md).

#### Spice Functions

{% hint style="info" %}
Spice Functions is in beta and initially available for Design Partners. Get in touch for more info.
{% endhint %}

Developers can now author [Spice Functions](broken-reference) in [Golang](broken-reference) with the Go1.x runtime in addition to [Python](broken-reference).

Combine Spice Functions with expanded Datasets and Views support to generate custom datasets "ETL-less" in the Spice platform that can be kept private or shared with others.

#### Datasets and Views

Spice now supports SQL migrations to enable creation of custom user-authored datasets and views.

**New In this Release**

1. \[Spice Functions] Add Go1.x runtime.
2. \[Datasets and Views] Add SQL migrations.
3. \[Datasets and Views] Add sharing and publishing.
4. \[Portal] Add basic charting for SQL and Firecache results.
5. \[Portal] Bugfixes and minor improvements to the UI.

### July 2023

The July release enables new compute over data capability with [Spice Functions](broken-reference) including application data storage, the ability to define and create custom datasets, and deep integration with GitHub.

#### Spice Functions

{% hint style="info" %}
Spice Functions is in beta and initially available for Design Partners. Get in touch for more info.
{% endhint %}

[Spice Functions](broken-reference) is a hosted compute experience that enables developers to write code in their preferred language and run it on the Spice platform, co-located with Spice data.

See [Broken link](broken-reference "mention") for full documentation on creating and deploying Spice Functions.

#### Spice Firecache

{% hint style="info" %}
Spice Firecache is in beta and initially available for Design Partners. Get in touch for more info.
{% endhint %}

[Spice Firecache](../building-blocks/spice-firecache/) is a real-time SQL cache that enables developers to cache Spice datasets for high concurrency, blazing fast SQL query up to 10x the performance of general SQL query.

The Spice platform completely manages the Spice Firecache data lifecycle, ensuring datasets are real-time updated on triggers like new blocks and with stale data being automatically evicted.

See [spice-firecache](../building-blocks/spice-firecache/ "mention") for full documentation on deploying datasets to the Spice Firecache.

#### Custom Datasets

Spice now supports the definition and creation of your own private Datasets and Views, which can then be queried with SQL, cached in Spice Firecache, and published publicly to be shared with others.

See [datasets-and-views.md](../building-blocks/datasets-and-views.md "mention") for full documentation on creating private Datasets and Views.

#### Connecting Github Repos

Connecting your Spice.xyz app to a GitHub repository allows you to create custom Datasets and Views, add datasets to Spice Firecache, author Spice Functions, and train AI Models.

See [connect-github-repository.md](../portal/apps/connect-github-repository.md "mention") for full documentation on connecting your Github Repo to a Spice App.

**New In this Release**

1. \[Platform/Portal] Support for compute over data with Spice Functions&#x20;
2. \[Platform/Portal] Real-time SQL caching through Spice Firecache
3. \[Platform/Portal] Support for custom datasets and views beyond those curated by Spice
4. \[Portal] Connect your Github repo to manage all your Spice code with version control
5. \[Flow] RPCs can now be sent to the Spice Flow node using the [Flow Access API](https://developers.flow.com/concepts/nodes/access-api)
6. \[Flow] Added datasets detailing transfers of NFTs and tokens on the Flow blockchain, for more details see [Broken link](broken-reference "mention")

**Changes**

1. \[Portal] Any users you add to your org that is on a Pro or Partner plan will now automatically be activated and removed from the Spice.xyz waitlist.

### June 2023

The June release includes new datasets for Ethereum/Goerli wallet balances + Flow core/nft datasets, additional platform performance upgrades along with several usability and user-experience improvements.

#### Wallet Balance Datasets

The wallet balances datasets contains a block-level view of all Ether balance changes due to gas fees, withdrawals, and committed external and internal (contract) transactions.

{% hint style="info" %}
Wallet Balances datasets do not yet have full historical data.
{% endhint %}

* [`eth.wallet_balances`](sql-query-tables/ethereum/wallet-balances/)
* [`goerli.wallet_balances`](sql-query-tables/goerli/token-tables-1/)

#### Flow Datasets

[Flow](broken-reference) is a fast, decentralized, and developer-friendly blockchain, designed as the foundation for a new generation of games, apps, and the digital assets that power them. Supercharge your Flow apps with these datasets indexed by Spice.xyz.

{% hint style="info" %}
Flow support is in preview. Contact us to let us know if Flow support is important to you!
{% endhint %}

* [`flow.blocks`](broken-reference)
* [`flow.transactions`](broken-reference)
* [`flow.events`](broken-reference)
* [`flow.nfts`](broken-reference)
* [`flow.nft_transfers`](broken-reference)
* [`flow.token_transfers`](broken-reference)

#### Portal

Portal UX improvements include the ability to search the dataset reference for specific datasets and inserting a sample query with a click. GitHub avatars now show up in the organization drop-down, as well as a distinction between your personal account and other organizations you are part of. Searching for members to add to an organization now properly autocompletes.

{% embed url="https://youtu.be/2qk8ZMZOJek" %}
[Spice.xyz](http://spice.xyz) SQL explorer dataset reference improvements
{% endembed %}

**New In this Release**

1. \[Wallet Balances] Added wallet balance datasets for Ethereum and Goerli which track changes to wallet balances on every block.
2. \[Flow] Added Flow datasets, including core and enriched NFT/token datasets.
3. \[Portal] Show GitHub avatars in the organization drop-down.
4. \[Portal] The organization drop-down now distinguishes between your personal account and other organizations you are part of.

**Changes**

1. \[Portal] You can now search for datasets in the dataset reference.
2. \[Portal] Sample queries can be injected into the query editor by clicking in the dataset reference.
3. \[Portal] Improved error messages in the SQL editor for syntax errors.
4. \[Portal] The dialog box used for adding organization members now auto-completes for potential members to add.
5. \[Performance] Improved performance for several datasets, including `eth.beacon.validators` and `goerli.beacon.validators`.

### May 2023

The May release includes significant platform performance upgrades with the rollout of Spice AI's **second generation platform architecture (Gen. 2)** along with several usability and user-experience improvements.

[Ethereum](sql-query-tables/ethereum/) and [Polygon](broken-reference) block latency (the time to process a block and make it available for query) is now **subsecond** for core data like blocks, transactions, and logs, and less than **2.5 seconds** for enriched data like [NFTs](broken-reference), [ENS](sql-query-tables/ethereum/token-tables-1/), [Uniswap](samples-and-examples/example-dex-queries/uniswap.md), and [Sushiswap](samples-and-examples/example-dex-queries/sushiswap.md). Query execution speed is now **1.5x-10x faster!**

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption><p><a href="samples-and-examples/example-ethereum-beacon-sql-queries/">Example Queries</a> referenced in docs are now <strong>1.5x-10x faster!</strong></p></figcaption></figure>

Portal UX improvements include the ability to collapse the sidebar, resize the SQL query input and results pane, and expand to a fullscreen focus mode. SQL query errors are now highlighted with red underline swiggles along with a more readable error pane. Finally, results render faster and app switching is faster.

{% embed url="https://youtu.be/ZJNt3paE7hA" %}
[Spice.xyz](http://spice.xyz) SQL explorer fullscreen mode
{% endembed %}

**New In this Release**

1. \[Platform] Spice AI's Second-Generation Platform Architecture (Gen. 2) resulting in 30-50% data latency improvements, 1.5x-10x faster queries, with a target availability of 99.9%.
2. \[Portal] SQL query editor contextual error reporting.
3. \[Portal] SQL query explorer fullscreen mode.
4. \[Portal] SQL query editor and results pane resizability.
5. \[Portal] Collapsable sidebar.
6. \[Portal] Page loading progress bar.

**Changes**

1. \[Portal] The portal now uses a [GitHub App](https://docs.github.com/en/apps) to integrate with GitHub. This will result in a request for re-authorization on the next sign-in.
2. \[Go SDK] [gospice v0.2.1](https://github.com/spiceai/gospice) released with [Prices API](broken-reference) and [Apache Arrow v12](https://pkg.go.dev/github.com/apache/arrow/go/v12) support.
3. \[Node.js SDK] [spice.js v0.3.2](https://github.com/spiceai/spice.js/releases) released with a fix to re-support Node 16.

### April 2023

This month we added new datasets including Chainlink prices data feeds, Aave v2 contract data, Ethereum Shanghai/Capella beacon and withdrawals data, and we now fully index the Goerli testnet. We also released the Goerli Beacon and Ethereum Beacon APIs. \
\
**Chainlink Data Feeds:** You can now leverage oracles for various data feed on the Chainlink network by querying prices specific tables including `eth.chainlink.prices` and `eth.chainlink.recent_prices`.

This includes accessing the latest, minute-precision data on `transaction_hash`, `oracle_address`, `block_timestamp`, price of the asset in WEI, `asset_address` and more. The columns and their schema available for each table can be viewed with the describe \<table> command:

<pre class="language-sql"><code class="lang-sql"><strong>/* Show the columns available */
</strong>DESCRIBE eth.chainlink.prices;
</code></pre>

Data for for [Curve](https://classic.curve.fi/whitepaper), [Balancer](https://balancer.fi/), [Aave](https://aave.com/), [Yearn](https://yearn.finance/), [DAI](https://makerdao.com/en/), [Tether USD](https://tether.to/en/about-us/) and 30 other top assets is available. See the full list of supported data feeds [here](https://docs.spice.xyz/reference/sql-query-tables/sql-query-tables/chainlink-tables/prices-tables).&#x20;

\
**Aave V2 Dataset:** In addition to the Aave token prices data feed on the Chainlink network, we have released indexed [Aave V2](sql-query-tables/ethereum/aave-v2-tables/) data for loans, collaterals and prices. You can query for the latest updates to Aave loans and collateral by querying `eth.aave_v2.loan_updates` and `eth.aave_v2.collateral_updates`.&#x20;

<figure><img src="../.gitbook/assets/Screen Shot 2023-05-09 at 9.49.27 AM.png" alt=""><figcaption><p>Latest view of all Aave V2 loans query, sample output</p></figcaption></figure>

\
**Ethereum Shanghai/Capella Upgrade and Withdrawals Datasets:** The [Ethereum Shanghai/Capella upgrade](https://blog.ethereum.org/2023/03/28/shapella-mainnet-announcement) is now full supported after its completion on April 12, 2023, 10:27:35pm UTC at epoch 194048.

The completion of Ethereum's Shanghai hard fork, also known as "Shapella," has authorized the withdrawal of funds for individuals who have "staked" their ETH to validate and secure blockchain transactions.

We also released the `eth.withdrawals` dataset to capture new withdrawals. For example, you can now query to get ETH withdrawn:

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

Explore detailed sample SQL queries for [DEX](samples-and-examples/example-dex-queries/), [Cross-Chain](samples-and-examples/example-cross-chain-queries.md), [Ethereum](broken-reference), [Beacon](samples-and-examples/example-ethereum-beacon-sql-queries/), and [Bitcoin](samples-and-examples/example-bitcoin-queries/) in the Spice Docs.\


**Goerli Testnet:** Full support for the Goerli testnet has been added, including hosted beacon and execution nodes, and fully indexed datasets, helping developers test their applications before mainnet launch.&#x20;

Available with realtime and historical data on [Spice.xyz](https://spice.xyz/), this includes Goerli base type tables, Goerli [token specific tables](https://docs.spice.xyz/reference/sql-query-tables/goerli/token-tables), and Goerli [Beacon Chain specific tables](https://docs.spice.xyz/reference/sql-query-tables/goerli/beacon-chain-tables). You can start by querying `goerli.traces`, `goerli.blocks` or a number of sample beacon queries.&#x20;

For example, you can query from `goerli.beacon.validators` to retrieve recently updated validators, with their balance and status:

<figure><img src="../.gitbook/assets/Screen Shot 2023-05-09 at 8.33.15 PM.png" alt=""><figcaption><p>Recently updated validators, with their balance and status by querying from <code>goerli.beacon.validators</code>, sample output</p></figcaption></figure>

**Goerli Beacon API:** You can easily retrieve requests like "[get validator balances from state](https://docs.spice.xyz/api/goerli/beacon-http-api)" using the **`https://data.spiceai.io/goerli/beacon`** API, which is compatible with the read-only GET requests from the [Beacon Node API specification](https://ethereum.github.io/beacon-APIs/).

All [Goerli testnet data APIs](broken-reference) are available at **/goerli/v0.1** including the following:

* [JSON RPC Methods](broken-reference)
* [Beacon HTTP API](broken-reference)
* [Blocks](broken-reference)
* [Contracts](broken-reference)
* [Gas Fees](broken-reference)

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
* \[Chainlink] added [price feed support](sql-query-tables/ethereum/chainlink-tables/) for the following assets:
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

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

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


    <figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>
3.  Top 10 most frequent block proposers\


    <figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

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

Spice supports querying [Polygon data](broken-reference) in addition to the existing [Ethereum](sql-query-tables/ethereum/) and [BItcoin](sql-query-tables/bitcoin/) datasets.

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

Spice now features DEX Liquidity and Events Dataset where users can access indexed liquidity data from UniSwap \[[V2](sql-query-tables/ethereum/uniswap-v2-tables/), [V3](sql-query-tables/ethereum/uniswap-v3-tables/)] and [SushiSwap](sql-query-tables/ethereum/sushiswap-tables/) liquidity pools, _within seconds_.&#x20;

Data is available both historically and in real time, providing unparalleled visibility on DEX liquidity pools.

**ENS (Preview)**\
You can now preview the new dataset for [Ethereum Name Service events](sql-query-tables/ethereum/token-tables-1/), available by querying `eth.ens`. Within the dataset, you’ll find that each ENS event will have its own table as immutable data.

This also includes the new `ens.domains` dataset, which is updated in real-time to have the latest `eth_address` whenever a transfer or name-registered event happens

Read more on the [Spice AI blog](https://blog.spice.ai/whats-new-b7f637897df8).

**Changes**

* [Prices dataset](broken-reference) now out of preview
* Added export to CSV results format in addition to existing formats [JSON](../api/ethereum/json-rpc-methods.md) and [Apache Arrow](../api/sql-query/apache-arrow-flight-api.md), for easy use with apps, ML, or libraries like NumPy and Pandas
* Added performance improvements for faster queries across existing datasets including `eth.traces`&#x20;

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### October 2022

Spice now has [prices dataset](broken-reference) in preview.&#x20;

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

Spice launches and tests [Polygon support](broken-reference).

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

Spice supports querying [Bitcoin data](sql-query-tables/bitcoin/) in addition to the existing [Ethereum datasets](sql-query-tables/ethereum/).

Read more on the [Spice AI blog](https://medium.com/spice-ai/).

**Changes**

* Support for fundamental Bitcoin datasets
  * `btc.blocks` / `btc.recent_blocks`
  * `btc.transactions` / `btc.recent_transactions`
  * `btc.transaction_inputs` / `btc.recent_transaction_inputs`
  * `btc.transaction_outputs` / `btc.recent_transaction_outputs`
* [example-bitcoin-queries](samples-and-examples/example-bitcoin-queries/ "mention") for querying Bitcoin data.

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### June 2022

This update includes a new [Javascript/Typescript SDK](../sdks/node.js-sdk/) for Node.js, an improved [Python SDK](../sdks/python-sdk/), and performance improvements for Ethereum tokens and NFT datasets.

[Ethereum Name Service (ENS)](sql-query-tables/ethereum/token-tables-1/) support is also available in beta with the new `ens.domains` dataset.

Read more on the [Spice AI blog](https://medium.com/spice-ai/spice-xyz-june-update-f74d60faff61).

**Changes**

* New [Node.js SDK](../sdks/node.js-sdk/)
* Improved [Python SDK](../sdks/python-sdk/)
* ENS support in beta
  * `ens.domains`
* Improved performance for `eth.tokens_` and `eth.nft_` prefixed tables

#### Resources

* [Getting started with Spice AI](https://docs.spice.xyz/get-started)
* [Documentation](https://docs.spice.xyz/)
* [FAQ](https://docs.spice.xyz/faq)



### May 2022

Spice now has some of the best automated token standard detection for erc20, erc721, and erc1155 tokens available. Tokens are detected by their signatures and as they emit events over time, so Spice provides a probability of standards compliance to each contract. Along with this support are now token-specific tables like `eth.tokens_erc1155` and `eth.token_transfers_erc20`. See the entire list [Tokens Tables](sql-query-tables/ethereum/token-tables/).

Performance is now even better, especially for larger queries, and for results over the HTTP API. We still recommend the [Apache Arrow Flight API](../api/sql-query/apache-arrow-flight-api.md) that's easily accessible via the [Python SDK](../sdks/python-sdk/) for production use though.

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
