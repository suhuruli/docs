---
description: Spice.xyz Release notes
---

# Release notes

### January 2023

Sharing a packed release this month focused on a new dataset, org management, two developer querying tools, and two SDKs.

**Ethereum Name Service (ENS) events** is now out of preview, available by querying `ens.domains`, which is updated in real-time to have the latest `eth_address`whenever a transfer or name-registered event happens. Both `eth.ens` and other on-demand events indexed under the `eth.ens` prefix such as `eth.ens_event_nameregistered` are updated in real time with the same high-performance standards of published Spice datasets. See the tables [here](https://docs.spice.xyz/reference/sql-query-tables/sql-query-tables/token-tables-1).

**Organization Management:** Existing users can start exploring org support and management for users, apps, and datasets by [authorizing Spice with read-only access](https://docs.spice.xyz/get-started/portal-login) when logging into the [Spice.xyz](http://spice.xyz/) portal. This will also act as a parent container for future concepts including apps, users, teams, datasets, and metrics for streamlined management and navigation within [spice.xyz](http://spice.xyz/).

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
