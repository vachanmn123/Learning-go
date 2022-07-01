# Hello World:

```go
package main

import (
  "fmt"
)

func main() {
  fmt.Println("Hello, World")
}
```
# Variable declaration:
The var statement declares a list of variables. the type is last. *Weird ik*

`var foo int, bar bool`

## Variables with initializers
A var declaration can include initializers, one per variable. If an initializer is present, the type can be omitted; the variable will take the type of the initializer.

`var i, j = 1, 2`

## Shorthand initialization
Inside a function,`:=` can be used in place of a var declaration with implicit type.

`k := 3`

**NOTE**: This is only available inside function bodies, not allowed outside functions!

## Parenthesis declarations

```go
var (
	boolean   bool       = false
	integer int     = 10
	string      string = "Funny String"
)
```

## Constant variables
Constants can be defined using the `const` keyword.

`const foo = "FOOOOOOOOOOOOO"`

**NOTE**: 
- Constants can be character, string, boolean, or numeric values. 
- Constants cannot be declared using the := syntax.

# Variable types:
Basic types in Go

- bool
- string
- int  int8  int16  int32  int64
- uint uint8 uint16 uint32 uint64 uintptr  <-- This is unsigned int
- byte
- rune
- float32 float64
- complex64 complex128

## Default(Zero) values of variables
- 0 for numeric types,
- false for the boolean type, and
- "" for strings.

🙏 much better than C

## Type conversions

```go
var x, y int = 3, 4
var f float64 = math.Sqrt(float64(x*x + y*y))
var z uint = uint(f)
```
**NOTE**: Unlike in C, assignment between items of different type requires an explicit conversion.

# For loop:
There is only one kind of loop in go, it is the `for` loop.

```go
sum := 0
for i := 0; i < 10; i++ {
	sum += i
	}
```
The basic `for` loop has three components separated by semicolons:

the init statement: executed before the first iteration (OPTIONAL)
the condition expression: evaluated before every iteration
the post statement: executed at the end of every iteration (OPTIONAL)

if the condition, init, post statements are all skipped, then it becomes infinite loop.

**NOTE**: {} always needed, () around params not allowed. `;` can also be skipped if not using init and post statements.



# Packages:
Every Go program is made up of packages.
Programs start running in package main.

```go
package main
```

# Imports:

```go
import "fmt"
import "math/rand"
```
OR
```go
import (
	"fmt"
	"math/rand"
)
```
Best practise is using parenthesis

# Exported Names:

A name is exported if it begins with a capital letter.

`Pizza` will be exported but `pizza` won't.

# Functions:

```go
func add(x int, y int) int {
	return x + y
}
```
**Note**: type is after variable name and return type is after the argument list. *Weird language*

shortcut here, When two or more consecutive named function parameters share a type, you can omit the type from all but the last.

```go
func add(x, y int) int {
	return x + y
}
```
## Multiple values can be returned by a function!!

```go
func swap(x, y string) (string, string) {
	return y, x
}
```

## Named return values
Go's return values may be named. If so, they are treated as variables defined at the top of the function. These names should be used to document the meaning of the return values.

```go
func split(sum int) (x, y int) {
	x = sum * 4 / 9
	y = sum - x
	return
}
```

