# eth.eigenlayer.eigenpods

The `eth.eigenlayer.eigenpods` table contains the current list of all [eigenpods](https://github.com/Layr-Labs/eigenlayer-contracts/blob/master/docs/EigenPods.md) that have been created, as determined by the event [PodDeployed](https://github.com/Layr-Labs/eigenlayer-contracts/blob/af8d8755fdad94705479679c7c63d454c4ed9a8e/src/contracts/pods/EigenPodManager.sol#L69). It includes the following fields:

| Column Name             | Data Type         | Description                                                                                   |
| ----------------------- | ----------------- | --------------------------------------------------------------------------------------------- |
| `eigenpod`              | CHARACTER VARYING | The smart contract address of the eigenpod.                                                   |
| `withdrawal_credential` | CHARACTER VARYING | The Beacon chain validator withdrawal credential that should match the eigenpod address.      |
| `pod_owner`             | CHARACTER VARYING | The address of the owner for this eigenpod.                                                   |
| `transaction_hash`      | CHARACTER VARYING | The hash of the transaction where this eigenpod was created.                                  |
| `log_index`             | BIGINT            | The index of the PodDeployed log event within the Ethereum block that created this eigenpod.  |
| `block_hash`            | CHARACTER VARYING | The hash of the block that contains the transaction which created this eigenpod.              |
| `block_timestamp`       | BIGINT            | The timestamp of the block that contains the transaction which created this eigenpod.         |
| `block_number`          | BIGINT            | The block number in the blockchain that contains the transaction which created this eigenpod. |
