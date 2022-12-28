---
description: Frequently asked questions
---

# FAQ

### What data sources do you have?

Spice currently supports [**Ethereum**](reference/sql-query-tables/), [**Bitcoin**](reference/sql-query-tables/bitcoin.md), and [**Polygon**](reference/sql-query-tables/polygon/) blockchain data and [**Sushiswap**](reference/sql-query-tables/ethereum/sushiswap-tables.md)**,** [**Uniswap-V2**](reference/sql-query-tables/ethereum/uniswap-v2-tables.md)**,** and [**Uniswap-V3**](reference/sql-query-tables/ethereum/uniswap-v2-tables.md) smart-contract data. We also have [**NFT**](reference/sql-query-tables/ethereum/nft-tables.md) and [**token**](reference/sql-query-tables/ethereum/token-tables.md) specific tables.

We have plans to add more chains and contracts prioritized by user feedback, along with other sources of data like more [Prices](api/prices.md). We expect to add **Solana** next.

For the all-up list, see [Datasets](datasets.md) and follow the [Release notes](reference/release-notes.md) for progress.

### How much does Spice cost?

Spice is currently in beta and it's free to [get an API key](https://spice.xyz).

We plan to always have a free tier and offer free APIs, like the [Gas Fees API](api/ethereum/gas-fees.md).

For customers who need higher request or query limits, service guarantees, or priority support we plan to offer high-value paid tiers based on usage.

### What level of support do you offer?

During the beta, we offer [best-effort support](broken-reference/) in our Discord. If you'd like higher-priority support or are interested in becoming a [Design Partner](https://www.craft.do/s/bgJFtYzSZwuFXD), please let us know.

### What SQL query engine/language do you support?

We currently use an [Apache Calcite](https://calcite.apache.org/) based query engine and support the ANSI SQL standard.

### Can you add \<table> / dataset?

Most likely, yes! Hit us up on Discord and we can work with you to add new views/tables. And the ability to create private custom tables is on our roadmap.

### Do you support WebSockets or other streaming?

WebSocket support is available for [Design Partners](https://www.craft.do/s/bgJFtYzSZwuFXD). Apache Arrow over gRPC streaming is on our roadmap.

### Do you support alerting?

Not yet, but it is on our roadmap.

### Do you support JDBC/ODBC?

Not yet, but it is on our roadmap.
