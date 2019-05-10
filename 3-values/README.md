# Golang Basic Value Types
Go has various value types including strings, integers, floats, booleans, etc.

## TL;DR Text
Defining Value:

Static Type definition:
```go
// status and bool are two different types.
type status bool
// MyString and string are two different types.
type MyString string
// Id and uint64 are two different types.
type Id uint64
// real and float32 are two different types.
type real float32

/* Some type alias declarations */

// boolean and bool denote the same type.
type boolean = bool
// Text and string denote the same type.
type Text = string
```

Dynamic type definition:
```go
    iAmString := "this is going to be known as string" //string
    iAmInt    := 1 //int
    iAmInt64  := 817236182736 // int64
    iAmFloat  := 3.2
    iAmBool   := true //boolean
```

Strings, which can be added together with +.
```go
    fmt.Println("go" + "lang")
```

Integers and floats.
```go
    fmt.Println("1+1 =", 1+1)
    fmt.Println("7.0/3.0 =", 7.0/3.0)
```

Booleans, with boolean operators as you’d expect.
```go
    fmt.Println(true && false)
    fmt.Println(true || false)
    fmt.Println(!true)
```

## Built-in Basic Types in Go
Go supports following built-in basic types:
    * one boolean built-in boolean type: `bool`.
    * 11 built-in integer numeric types: `int8`, `uint8`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, `int`, `uint`, and `uintptr`.
    * two built-in floating-point numeric types: `float32` and `float64`.
    * two built-in complex numeric types: `complex64` and `complex128`.
    * one built-in string type: `string`.


Go also support two built-in type aliases,
    * `byte` is a built-in alias of `uint8`. We can view `byte` and `uint8` as the same type.
    * `rune` is a built-in alias of `int32`. We can view `rune` and `int32` as the same type.

The integer types whose names starting with an u are unsigned types. Values of unsigned types are always non-negative. The number in the name of a type means how many binary bits a value of the type will occupy in memory at run time. For example, every value of the uint8 occupies 8 bits in memory. So the largest uint8 value is 255 (28-1), the largest int8 value is 127 (27-1), and the smallest int8 value is -128 (-27).

If a value occupies N bits in memory, we say the size of the value is N bits. The sizes of all values of a type are always the same, so value sizes are often called as type sizes.

We often measure the size of a value based on the number of bytes it occupies in memory. One byte contains 8 bits. So the size of the uint32 type is four bytes.

The sizes of int and uint values in memory are operation system dependent, either 32 or 64 bits. The size of uintptr value must be large enough to store the uninterpreted bits of any memory address.

The real and imaginary parts of a complex64 value are both float32 values, and the real and imaginary parts of a complex128 value are both float64 values.

In memory, all floating-point numeric values in Go are stored in IEEE-754 format.

A boolean value represents a truth. There are only two possible boolean values in memory, they are denoted by the two predeclared named constants, false and true. Name constants will be introduced in the next article.

In logic, a string value denotes a piece of text. In memory, a string value stores a sequence of bytes, which is the UTF-8 encoding representation of the piece of text denoted by the string value. We can learn more facts on strings from the article strings in Go later.

Although there is only one built-in type for each of boolean and string types, we can define custom boolean and string types for the built-in boolean and string types. So there can be many boolean and string types. The same is for any kinds of numeric types. The following are some type declarations examples. In these declarations, the word type is a keyword.

```go
/* Some type definition declarations */

// status and bool are two different types.
type status bool
// MyString and string are two different types.
type MyString string
// Id and uint64 are two different types.
type Id uint64
// real and float32 are two different types.
type real float32

/* Some type alias declarations */

// boolean and bool denote the same type.
type boolean = bool
// Text and string denote the same type.
type Text = string
// U8, uint8 and byte denote the same type.
type U8 = uint8
// char, rune and int32 denote the same type.
type char = rune
```

## Zero Values
Each type has a zero value. The zero value of a type can be viewed as the default value of the type.
    * The zero value of a boolean type a false truth.
    * The zero value of a numeric type is zero, though zeros of different numeric types may have different sizes in memory.
    * The zero value of a string type is an empty string.


## Boolean value literals
Go specification doesn't define boolean literals. However, in general programming, we can view the two predeclared identifiers, false and true, as boolean literals. But we should know that the two are not literals in the strict sense.

As above has mentioned, zero values of boolean types are denoted with the predeclared false constant.

## Integer value literals
There are three integer value literal forms, the decimal (base 10) form, the octal (base 8) form and the hex (base 16) form. For example, the following three integer literals all denote `15` in decimal.

```go
0xF // the hex form (starts with a "0x" or "0X")
017 // the octal form (starts with a "0")
15  // the decimal form (starts without a "0")
```

The following program will print two true texts.

```go
package main
import "fmt"
func main() {
	fmt.Println(15 == 017) // true
	fmt.Println(15 == 0xF) // true
}
```

Note, the two `==` are the equal-to comparison operator, which will be introduced in common operators.

Generally, zero values of integer types are denoted as `0` in literal, though there are many other legal literals for integer zero values, such as `00` and `0x0`. In fact, the zero value literals introduced in the current article for other kinds of numeric types can also represent the zero value of any integer type.

## Floating-point value literals
A floating-point value literal can contain an integer part, a decimal point, a fractional part, and an exponent part. Some parts can be omitted. Example:

```go
1.23
01.23 // == 1.23
.23
1.
// A "e" or "E" starts the exponent part.
1.23e2  // == 123.0
123E2   // == 12300.0
123.E+2 // == 12300.0
1e-1    // == 0.1
.1e0    // == 0.1
0e+5    // == 0.0
```

The standard literals for zero value of floating-point types are `0.0`, though there are many other legal literals, such as `0.`, `.0`, `0e0`, etc. In fact, the zero value literals introduced in the current article for other kinds of numeric types can also represent the zero value of any floating-point type.



## Resources
Read More here:

[go101](https://go101.org/article/basic-types-and-value-literals.html)


## Navigate
[List Of Content](../README.md)

Back To Previous Article: [<< Hello World in Golang](../2-hello-world/README.md)

