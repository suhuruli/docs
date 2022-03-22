# Limitations

In beta, Spice has a number of limitations, including:

#### Global API Limits

* 10 apps per account.
* 10 request-per-second (rps).
* 90-second request/query timeout.
* 500 row limit for HTTP API results.

#### Guest API Limits - No API Key

* 4 request-per-minute SQL API limit.

**Apache Flight Endpoint**

* API Key (provided as gRPC password) is always required.

**SQL Query Limits**

* 3 concurrent-requests.

#### Data Limitations (as of Mar 22, 2022)

* 99.99% data complete on core Ethereum types (blocks, transactions).
* DEX (Sushiswap, Uniswap, etc) pool data for the last month only, tracking the top 1000 pools by TVL/Market Cap.
* 128-bit integer limit (while data can be uint256). We include both the 128-bit `DECIMAL(38)` type and  `_hex` fields where the type is 256-bit.
* Support for erc20 and erc721. No support for erc1155 yet and token standard detection currently does not work for proxy contracts.
