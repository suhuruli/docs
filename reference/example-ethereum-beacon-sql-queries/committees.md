# Committees

### Committees Number Statistics

Average number of committees per slot (i.e., average number of committee indices per slot).

**Typical query time**: <<mark style="color:red;">**???**</mark> seconds

<pre class="language-sql"><code class="lang-sql">SELECT 
  AVG(num_committees) AS average_num_committees_per_slot
FROM (
  SELECT
    block_slot, 
    COUNT(1) AS num_committees
<strong>  FROM 
</strong><strong>    eth_beacon_committees
</strong>  GROUP BY 
    block_slot
) AS commitees_per_slot
</code></pre>

### Validators per Committee

Average number of validators per committee

**Typical query time**: <<mark style="color:red;">**???**</mark> seconds

```sql
SELECT 
  AVG(num_validators) AS average_num_validators_per_committee 
FROM (
  SELECT 
    block_slot, 
    cardinality(committee) AS num_validators
  FROM eth.beacon.committees
) AS validators_per_committee
```
