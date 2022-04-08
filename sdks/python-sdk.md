# Python SDK

The Python SDK `spicepy` is the easiest way to use and query Spice in Python.

### Requirements

* Python 3.7+

The following packages are required and will be automatically installed by pip:

* `pyarrow`
* `pandas`

**Note**: M1 Macs require an M1 compatible version of `pyarrow` which can be installed using [Anaconda](https://www.anaconda.com):

```
conda install -c conda-forge pyarrow
```

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
block_data = client.query('SELECT * FROM eth.recent_blocks LIMIT 10;')
transcation_Data = client.query('SELECT * FROM eth.transactions LIMIT 10;')
```

`Client` objects has the following arguments:

* **key** (required) : the API key too authenticate with.
* **url** (optional) : URL to the endpoint to connect to (default: grpc+tls://flight.spiceai.io).
* **tls\_root\_cert** (optional): path to specific certificate to use for the TLS connection.
