# Python SDK

The Python SDK `spicepy` is the easiest way to use and query Spice in Python.

### Requirements

* Python 3.7+

The following packages are required and will be automatically installed by pip:

* `pyarrow`
* `pandas`

#### M1 Macs

M1 Macs require an M1 compatible version of `pyarrow` which can be installed using [miniforge](https://github.com/conda-forge/miniforge). We recommend the following procedure:

1. Install [Homebrew](https://brew.sh)
2. Install [miniforge](https://github.com/conda-forge/miniforge) with `brew install --cask miniforge`
3. Initialize conda in your terminal with `conda init "$(basename "${SHELL}")"`
4. Install `pyarrow` and `pandas` with `conda install pyarrow pandas`

{% hint style="info" %}
While [Anaconda](https://www.anaconda.com) can be used to install pyarrow, the installed version is old (4.0.0) so we recommend using [miniforge](https://github.com/conda-forge/miniforge).
{% endhint %}

### Installation

Install the `spicepy` package directly from the Spice Github Repository at [https://github.com/spicehq/spice-py](https://github.com/spicehq/spice-py):

```
pip install git+https://github.com/spicehq/spice-py
```

### Usage

Import `spicepy` and create a `Client` by providing your API Key.

You can then submit queries using the query function.

```python
import spicepy
client = spicepy.Client('API_KEY')
block_data = client.query('SELECT * FROM eth.recent_blocks LIMIT 10;').read_pandas()
transaction_Data = client.query('SELECT * FROM eth.transactions LIMIT 10;').read_pandas()
```

`Client` objects has the following arguments:

* **key** (required) : the API key too authenticate with.
* **url** (optional) : URL to the endpoint to connect to (default: grpc+tls://flight.spiceai.io).
* **tls\_root\_cert** (optional): path to specific certificate to use for the TLS connection.
