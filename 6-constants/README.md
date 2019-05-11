# Constants
Constants are declared like variables, but with the const keyword.

Constants can be `character`, `string`, `boolean`, or `numeric values`.

Constants **cannot be declared using the := syntax**.

```go
package main

import "fmt"

const Pi = 3.14

func main() {
	const World = "世界"
	fmt.Println("Hello", World)
	fmt.Println("Happy", Pi, "Day")

	const Truth = true
	fmt.Println("Go rules?", Truth)
}
```

Edit and Run `go run constants.go` and observe the results.

## Numeric Constants
Numeric constants are high-precision values.

An untyped constant takes the type needed by its context.

Try printing `needInt(Big)` too.

(An `int` can store at maximum a 64-bit integer, and sometimes less.)

```go
const (
	// Create a huge number by shifting a 1 bit left 100 places.
	// In other words, the binary number that is 1 followed by 100 zeroes.
	Big = 1 << 100
	// Shift it right again 99 places, so we end up with 1<<1, or 2.
	Small = Big >> 99
)

func needInt(x int) int { return x*10 + 1 }
func needFloat(x float64) float64 {
	return x * 0.1
}

func main() {
	fmt.Println(needInt(Small))
	fmt.Println(needFloat(Small))
	fmt.Println(needFloat(Big))
}
```

## Navigate
[<< Basic Value Types](../5-value-types/README.md) | [List Of Content](../README.md) | [For >>](../7-for/README.md)