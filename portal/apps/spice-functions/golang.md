---
description: Creating a Spice Function in Go
---

# Golang

### Function Handlers

In the `function.yaml` , code execution runtime and invocation handler is defined.

<details>

<summary>Example <code>function.yaml</code> for a Go function</summary>

```yaml
# hello_world/function.yaml
output_dataset: hello_world
# This will trigger the function to execute on every new Ethereum block.
triggers:
  - path: eth
# This selects the runtime that will execute your code.
runtime: go1.x
# For Go, handler is [file_name_with_main].go
# The below will invoke the main method in a file `spice_function.go`.
handler: spice_function.go
```

</details>

See [Spice Functions YAML Specification](../../../reference/specifications/spice-functions-yaml-specification/) for the full YAML schema.

### Function Handlers

To implement a Function handler in Go, use the [spice-functions-go](https://github.com/spiceai/spice-functions-go) package.

1. Get the `spice-functions-go` package:

```bash
go get github.com/spiceai/spice-functions-go
```

2. Wrap the function handler with the spice-functions-go handler.

```go
// main.go
package main

import (
	"fmt"
	"github.com/spiceai/spice-functions-go/function"
	"github.com/spiceai/gospice/v2"
)

func hello(ctx *function.FunctionCtx, duckDb *sql.DB, spice_client *gospice.SpiceClient) error {
	fmt.Println("Hello Spice Functions!")
	return nil
}

func main() {
	function.Run(hello)
}
```

A Go invocation handler method has the following signature:

```go
func hello(ctx *function.FunctionCtx, duckDb *sql.DB, spice_client *gospice.SpiceClient) error
```

* `ctx`: A `context.Context` struct with additional getter funcs, E.g. `BlockNumber()` and `BlockHash()`
* `duckDb`: A connection to the Spice Function's DuckDB instance.
* `spice_client`: A [spicepy](https://github.com/spiceai/spicepy) client that is pre-initialized with the Spice app's API Key.

The handler method will be called on each triggered event.

### Example Function

An example Go function:

```go
// main.go
package main

import (
	"fmt"
	"github.com/spiceai/spice-functions-go/function"
	"github.com/spiceai/gospice/v2"
)

func hello(ctx *function.FunctionCtx, duckDb *sql.DB, spice_client *gospice.SpiceClient) error {
	fmt.Println("Hello Spice Functions!")
	return nil
}

func main() {
	function.Run(hello)
}
```
