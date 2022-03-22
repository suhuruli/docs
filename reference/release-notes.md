---
description: Spice Data Release notes
---

# Release notes

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

