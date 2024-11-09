# Signals

[![Go Reference](https://pkg.go.dev/badge/github.com/matthewmueller/signals.svg)](https://pkg.go.dev/github.com/matthewmueller/signals)

Easily cancel `context.Context` from OS signals.

## Install

```sh
go get github.com/matthewmueller/signals
```

## Example

```go
package main

import (
	"context"
	"os"
	"syscall"

	"github.com/matthewmueller/signals"
)

func main() {
	ctx := signals.Trap(context.Background(), os.Interrupt, syscall.SIGTERM)
	doSomething(ctx)
}
```

## Development

First, clone the repo:

```sh
git clone https://github.com/matthewmueller/signals
cd signals
```

Next, install dependencies:

```sh
go mod tidy
```

Finally, try running the tests:

```sh
make test
```

## License

MIT
