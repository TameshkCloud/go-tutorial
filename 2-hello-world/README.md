
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

## Navigate
[Main Page](../README.md)

Back To Previous Article: [<< Golang Installation](../1-installation/README.md)