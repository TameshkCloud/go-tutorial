# Hello World in Golang
Our first program will print the classic “hello world” message.

Create a file named `hello-world.go` and type this codes to write your first piece of golang code!

```go
package main
import "fmt"
func main() {
    fmt.Println("hello world")
}
```
You can find this file [hello-world.go](./hello-world.go)

To run the program, use `go run` :

```bash
$ go run hello-world.go
hello world
```

Sometimes we’ll want to build our programs into binaries. We can do this using `go build`:

```bash	
$ go build hello-world.go
$ ls
hello-world	hello-world.go
```

We can then execute the built binary directly.

```bash
$ ./hello-world
hello world
```

So Let's explain this hello world for you!

##  Packages
Every Go program is made up of packages.

Programs start running in package `main`.

This program is using the packages with import paths `"fmt"` and `"math/rand"`.

By convention, the package name is the same as the last element of the import path. For instance, the `"math/rand"` package comprises files that begin with the statement `package rand`.

Note: The environment in which these programs are executed is deterministic, so each time you run the example program r`and.Intn` will return the same number.

(To see a different number, seed the number generator; see `rand.Seed`. Time is constant in the playground, so you will need to use something else as the seed.)

```go
package main

import (
	"fmt"
	"math/rand"
)

func main() {
	fmt.Println("My favorite number is", rand.Intn(10))
}
```

## Imports
This code groups the imports into a parenthesized, "factored" import statement.

You can also write multiple import statements, like:

```go
import "fmt"
import "math"
```

But it is good style to use the factored import statement.

```go
package main

import (
	"fmt"
	"math"
)

func main() {
	fmt.Printf("Now you have %g problems.\n", math.Sqrt(7))
}
```

## Exported names
In Go, a name is exported if it begins with a capital letter. For example, `Pizza` is an **exported name**, as is `Pi`, which is exported from the `math` package.

`pizza` and `pi` do not start with a capital letter, so they are not exported.

When importing a package, you can refer only to its exported names. Any "unexported" names are not accessible from outside the package.

**Run the code. Notice the error message.**

To fix the error, rename `math.pi` to `math.Pi` and try it again:

```go
package main

import (
	"fmt"
	"math"
)

func main() {
	fmt.Println(math.pi)
}
```


## Navigate
[<< Golang Installation](../1-installation/README.md) | [List Of Content](../README.md) | [Functions >>](../3-functions/README.md)