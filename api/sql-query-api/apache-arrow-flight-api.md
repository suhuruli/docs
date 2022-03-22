---
description: Querying Ethereum data with SQL via the Apache Arrow Flight API
---

# Apache Arrow Flight API



SQL query results are now available as [Apache Arrow](https://arrow.apache.org) data frames via a high-performance [Apache Arrow Flight](https://arrow.apache.org/docs/format/Flight.html) endpoint.

Arrow Flight is a data protocol built on the high-performance, open-source [gRPC](https://grpc.io) protocol.&#x20;

This enables high-speed access to your data in [Python](https://arrow.apache.org/docs/python/index.html), [Go](https://pkg.go.dev/github.com/apache/arrow/go/v8), [C++](https://arrow.apache.org/docs/cpp/index.html), [C#](https://github.com/apache/arrow/blob/master/csharp/README.md), and [Rust](https://docs.rs/arrow-flight/latest/arrow\_flight/), and makes it easy to use libraries like [Pandas](https://arrow.apache.org/docs/python/pandas.html) and [NumPy](https://arrow.apache.org/docs/python/numpy.html?highlight=numpy#).

#### Connecting to the endpoint

* Use the gRPC + TLS URL: `grpc+tls://flight.spiceai.ai`
* Use basic authentication
  * Username can be set to an empty string
  * Password should be set to the API key of your app

#### Requirements

* [Table](broken-reference) names must be fully-qualified. For example `eth.blocks`

#### Samples

Find code samples in Python on [this page](broken-reference).

#### Mac/Windows Certificate issue

If you get this error:

`Could not get default pem root certs`

Install the [gRPC root certificates](https://github.com/googleapis/google-cloud-cpp/blob/main/google/cloud/bigtable/examples/README.md#configure-environment)

For macOS:

First download the `roots.pem` file from the google server:

```bash
curl -Lo roots.pem https://pki.google.com/roots.pem 
```

Before running your code/jupiter the environment variable GRPC\_DEFAULT\_SSL\_ROOTS\_FILE\_PATH must be set to point at the location of the file. If you are using command from a terminal this can be done from the folder containing `roots.pem` with:

```bash
export GRPC_DEFAULT_SSL_ROOTS_FILE_PATH="$PWD/roots.pem"
```

The `export` command will set this variable for this specific terminal (if you have tabs the other are unaffected). Thus will need to be run every time you open a new terminal.

Note that `$PWD` is a bash specific variable that will be replaced by the current directory path. You can download the certificate file `roots.pem` in a specific location and inform this path instead of `$PWD`.

For Windows:

```powershell
@powershell -NoProfile -ExecutionPolicy unrestricted -Command ^
    (new-object System.Net.WebClient).Downloadfile( ^
        'https://pki.google.com/roots.pem', 'roots.pem')
set GRPC_DEFAULT_SSL_ROOTS_FILE_PATH=%cd%\roots.pem
```
