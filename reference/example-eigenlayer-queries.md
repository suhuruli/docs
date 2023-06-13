# Example EigenLayer Queries

#### Native Staking Balances

```sql
select val.*, bls.from_bls_pubkey, bls.to_execution_address, bls.signature
from goerli.beacon_validators val
inner join goerli.eigenlayer.eigenpods pods on pods.withdrawal_credential = val.withdrawal_credentials
left join goerli.beacon_bls_to_execution_changes bls on val.validator_index = bls.validator_index
```

#### Value of recent withdrawals

<pre class="language-sql"><code class="lang-sql">SELECT COALESCE (SUM(w.amount), 0)
FROM goerli.beacon.recent_withdrawals w
<strong>JOIN goerli.eigenlayer.eigenpods pods ON pods.eigenpod = w.address
</strong></code></pre>

#### Eigenpod Balances

```sql
with currentBalances as (
    select eigenpod_address, balance_delta
    from goerli.eigenlayer.eigenpod_balances
    WHERE block_timestamp BETWEEN UNIX_TIMESTAMP('2023-06-01 00:00:00') AND UNIX_TIMESTAMP('2023-06-09 23:59:59')
)

SELECT SUM(balance_delta) balance_change
FROM goerli.eigenlayer.eigenpods pods
LEFT JOIN currentBalances ON pods.eigenpod = currentBalances.eigenpod_address
```

####
