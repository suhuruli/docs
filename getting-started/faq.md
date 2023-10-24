---
description: Frequently asked questions
---

# FAQ

### What data sources do you have?

Spice.ai is preloaded with select Web3 datasets from [**Ethereum**](../reference/sql-query-tables/) (including [**Beacon**](../reference/sql-query-tables/goerli/beacon-chain-tables/) & [**Goerli**](../reference/sql-query-tables/goerli/)), [**Bitcoin**](../reference/sql-query-tables/bitcoin/), and [**Polygon**](../reference/sql-query-tables/polygon/) blockchain data along with [**ENS**](../reference/sql-query-tables/ethereum/token-tables-1/), **DeFi/DEX** ([**Sushiswap**](../reference/sql-query-tables/ethereum/sushiswap-tables/)**,** [**Uniswap-V2**](../reference/sql-query-tables/ethereum/uniswap-v2-tables/)**,** [**Uniswap-V3**](../reference/sql-query-tables/ethereum/uniswap-v2-tables/)**,** [**Aave**](../reference/sql-query-tables/ethereum/aave-v2-tables/)), [**NFT**](broken-reference/) and [**token**](../reference/sql-query-tables/ethereum/token-tables/) specific data. Spice.ai also features a comprehensive set of [EigenLayer datasets](../reference/sql-query-tables/ethereum/eigenlayer-tables/).

Digital asset/cryptocurrency [spot/latest](broken-reference/) and full [historical prices](broken-reference/) data is available from leading exchanges including Coinbase, Gemini, and Binance.

More datasets are added each month prioritized by user feedback every month.

For the all-up list, see [Web3 Data](../building-blocks/datasets.md) and follow the [Release notes](../reference/release-notes.md) for updates.

### How much does Spice cost?

It's free to [get an API key](https://spice.ai) to use the [Community Edition](pricing/community-edition.md).

We plan to always have a free tier and offer free APIs, like the [Gas Fees API](../api/ethereum/gas-fees.md).

For customers who need higher request or query limits, service guarantees, or priority support we offer [high-value paid tiers](pricing/) based on usage.

### What level of support do you offer?

We offer [best-effort community support](https://github.com/spicehq/cloud-docs/blob/trunk/broken-reference/README.md) in Discord.

If you'd like higher-priority support or need enterprise-grade support with an SLA, [upgrade your plan](pricing/).

### What SQL query engine/language do you support?

We currently use an [Apache Calcite](https://calcite.apache.org/) based query engine and support the ANSI SQL standard.

[Spice Firecache](../reference/specifications/dataset-and-view-yaml-specification/firecache.md) is built on [DuckDB](https://duckdb.org/) and uses the DuckDB SQL dialect.

### Can you add \<table> / dataset or index a specific on-chain contract?

Most likely, yes! Hit us up on Discord and we can work with you to add new views/tables or index new contracts. We also support [custom views and datasets](../building-blocks/datasets-and-views.md).

### Do you support WebSockets or other streaming?

WebSocket support is available for [Enterprise](pricing/) customers. Apache Arrow over gRPC streaming is on our roadmap.

### Do you support alerting?

Not yet, but it is on our roadmap. You can also build your own custom alerting using [Spice Functions](../building-blocks/spice-functions/).

### Do you support JDBC/ODBC/ADBC?

Not yet, but it is on our roadmap.
