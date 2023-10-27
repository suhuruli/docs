---
description: Goerli JSON-RPC Methods Documentation
---

# JSON RPC Methods

The **`https://data.spiceai.io/goerli`** API is a [Ethereum JSON-RPC](https://eth.wiki/json-rpc/api) compatible endpoint for the Goerli testnet that can be used with web3 clients like [web.js](https://web3js.readthedocs.io), [ether.js](https://docs.ethers.io), and [web3.py](https://web3py.readthedocs.io).

Both libraries have great documentation on individual methods and the complete list can be found in the [specification](https://playground.open-rpc.org/?schemaUrl=https://raw.githubusercontent.com/ethereum/eth1.0-apis/assembled-spec/openrpc.json\&uiSchema%5BappBar%5D%5Bui:splitView%5D=false\&uiSchema%5BappBar%5D%5Bui:input%5D=false\&uiSchema%5BappBar%5D%5Bui:examplesDropdown%5D=false).

Spice supported methods are:

* `eth_protocolVersion`
* `eth_gasPrice`
* `eth_blockNumber`
* `eth_call`
* `eth_chainId`
* `eth_getBalance`
* `eth_getStorageAt`
* `eth_getTransactionCount`
* `eth_getBlockTransactionCountByHash`
* `eth_getBlockTransactionCountByNumber`
* `eth_getUncleCountByBlockHash`
* `eth_getUncleCountByBlockNumber`
* `eth_getCode`
* `eth_estimateGas`
* `eth_getBlockByHash`
* `eth_getBlockByNumber`
* `eth_syncing`
* `eth_getTransactionByHash`
* `eth_getTransactionByBlockHashAndIndex`
* `eth_getTransactionByBlockNumberAndIndex`
* `eth_getTransactionReceipt`
* `eth_getUncleByBlockHashAndIndex`
* `eth_getUncleByBlockNumberAndIndex`
* `eth_getWork`
* `eth_feeHistory`
* `eth_maxPriorityFeePerGas`
* `web3_clientVersion`
