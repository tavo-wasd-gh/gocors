# gocors

## Sample usage

```go
package main

import (
	"fmt"
	"net/http"

	"github.com/tavo-wasd-gh/gocors"
)

func endpoint(w http.ResponseWriter, r *http.Request) {
	// Allowed:        origins         methods         headers  creds
	if !cors.Handler(w, r, "*", "GET, OPTIONS", "Content-Type", false) {
		return
	}

	// Endpoint logic
	fmt.Fprintln(w, "Hello world after valid CORS headers")
}

func main() {
	http.HandleFunc("/endpoint", endpoint)
	http.ListenAndServe(":8080", nil)
}
```
