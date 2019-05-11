# Functions
A function can take zero or more arguments.

In this example, `add` takes two parameters of type `int`.

Notice that the type comes after the variable name.

```go
package main

import "fmt"

func add(x int, y int) int {
	return x + y
}

func main() {
	fmt.Println(add(42, 13))
}
```

When two or more consecutive named function parameters share a type, you can omit the type from all but the last.

In this example, we shortened

```go
x int, y int
```

to

```go
x, y int
```

Check this out:

```go
package main

import "fmt"

func add(x, y int) int {
	return x + y
}

func main() {
	fmt.Println(add(42, 13))
}
```

Read More: [Go's Declaration Syntax](https://blog.golang.org/gos-declaration-syntax)

## Navigate
[<< Hello WOrld in Golang](../2-hello-world/README.md) | [List Of Content](../README.md) | [Variables >>](../4-variables/README.md)