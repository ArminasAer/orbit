# 💫 Orbit 🪐

#### Version: 0.0.2

### HTTP wrapper for net/http and go-chi/chi

#### Who is this for?

This library is for my personal usage and knowledge

#### Features [not all baked in yet]

- Routing from [go-chi/chi](https://github.com/go-chi/chi)
  - chi router has been manually extended by orbit, will not be on the same track as the original project
  - all credit to [pkieltyka](https://github.com/pkieltyka)
- Context (Bits) wrapper
  - HTTP helper functions
  - HTML Template rendering
  - possible state injection
- Handler returns an error

#### Is this production ready?

No :D - this may never be production ready

### Installation

```sh
go get github.com/ArminasAer/orbit
```

### Example

```go
package main

import (
	"github.com/ArminasAer/orbit"
)

func main() {
	o := orbit.NewPlanet()

	o.Get("/", idHandler)

	o.Get("/{id}", )

	o.Launch("127.0.0.1:9000")
}

func idHandler(b orbit.Bits) error {
		id := orbit.URLParam(b.Request(), "id")

		return b.Text(200, id)
}
```

#### Inspired by:

- Chi
  - it is built on top of the chi router
- Echo
  - all handlers return an error
  - context interface paradigm
- Fiber
  - simple design
  - helper functions
- Express
  - express like patterns
- Axum
  - axum global state management
