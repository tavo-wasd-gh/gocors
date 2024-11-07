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
	if cors.Handler(w, r, "POST, GET, OPTIONS") {
		return
	}

	fmt.Fprintln(w, "Request handled")
}

func main() {
	http.HandleFunc("/endpoint", endpoint)
	http.ListenAndServe(":8080", nil)
}
```
