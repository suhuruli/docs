---
description: Spice Data Release notes
---

# Release notes

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

### Feb 2022

Significant upgrades in performance and data completeness. Adds the ability to query Ethereum, Sushiswap, and Uniswap data with SQL. Adds an Apache Flight endpoint.

#### Changes

* Adds SQL query
* Adds Sushiswap, Uniswap-V2, and Uniswap-V3 liquidity data
* Adds Apache Flight endpoint
* Adds management portal
* Significantly improved performance with the ability to query across real-time and historical data

### Jan 2022

Initial release of the Spice beta!

#### Changes

* The Initial release of the Spice Private Beta!
* Adds `/eth/v0.1/gasfees` API.
* Adds `/eth/v0.1/contracts` API.
* Adds `/v0.1/prices` API.

