# go-diff
A simple diff library for Go.

## Usage
### Install
Add go-diff to your project.

```sh
go get github.com/ktnyt/go-diff
```

### Character diff
```go
package main

import (
	"fmt"

	"github.com/ktnt/go-diff"
)

func main() {
	ops := diff.Diff("coelacanth", "pelican")

	// Output: copelaicanth
	fmt.Println(ops.Concat())
}
```

### Line diff
```go
package main

import (
	"fmt"

	"github.com/ktnt/go-diff"
)

func main() {
	ops := diff.LineDiff("foo\nbar\nbaz", "foo\nbaz\nbar")

	// Output:
	// |       foo
	// -       bar
	// |       baz
	// +       bar
	fmt.Println(ops.Join())
}
```
