---
description: SQL table schema for eth.wallet_lst_balances
---

# eth.wallet\_lst\_balances

Wallet balance changes for LSTs (Liquid Staking Tokens) on Ethereum.

Whenever the balance of a wallet holding one of the supported LSTs changes, a row is added to this dataset.

The supported LSTs are:

* [Rocket Pool Ether (rETH)](https://etherscan.io/address/0xae78736Cd615f374D3085123A210448E74Fc6393)
* [Lido Staked Ether (stETH)](https://etherscan.io/address/0xae7ab96520de3a18e5e111b5eaab095312d7fe84)
* [Coinbase Staked Ether (cbETH)](https://etherscan.io/address/0xBe9895146f7AF43049ca1c1AE358B0541Ea49704)

| Column                  | Data Type | Description                                                                    |
| ----------------------- | --------- | ------------------------------------------------------------------------------ |
| `address`               | TEXT      | The wallet address that contains this LST balance.                             |
| `token_address`         | TEXT      | The LST token address of the balance.                                          |
| `balance`               | DECIMAL   | Scaled balance (from the token's decimals) of the token.                       |
| `balance_delta`         | DECIMAL   | The change in balance from the previous block, scaled by the token's decimals. |
| `balance_raw`           | TEXT      | The raw balance of the token as a decimal string.                              |
| `balance_raw_hex`       | TEXT      | The raw balance of the token as a hex string.                                  |
| `balance_raw_delta`     | TEXT      | The change in balance from the previous block as a decimal string.             |
| `balance_raw_delta_hex` | TEXT      | The change in balance from the previous block as a hex string.                 |
| `balance_usd`           | DECIMAL   | The USD balance of this wallet at this block for the token.                    |
| `balance_eth`           | DECIMAL   | The ETH balance of the wallet at this block for the token.                     |
| `block_timestamp`       | BIGINT    | The timestamp of the block when this wallet had this balance.                  |
| `block_number`          | BIGINT    | The block number when this wallet had this balance.                            |
| `block_hash`            | TEXT      | The hash of the block when this wallet had this balance.                       |
