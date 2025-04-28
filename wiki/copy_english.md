<!--
Meta Description: # Copy in Go: Understanding the Copy Functionality in Go Programming Language ## Synopsis The `copy` function in Go is a built-in function that allows...
Meta Keywords: dst, copy, src, elements, slice
-->

# Copy in Go: Understanding the Copy Functionality in Go Programming Language

## Synopsis
The `copy` function in Go is a built-in function that allows developers to copy elements from one slice to another. It is essential for efficiently managing data in Go applications.

## Documentation
The `copy` function in Go is defined as follows:

```go
func copy(dst, src []Type) int
```

### Purpose
The primary purpose of the `copy` function is to copy elements from a source slice (`src`) to a destination slice (`dst`). The number of elements copied is determined by the smaller of the two slices. This function is useful for duplicating data, manipulating slices, or when you need to transfer data between slices with different lengths.

### Usage
- **Parameters**:
  - `dst`: The destination slice where elements will be copied.
  - `src`: The source slice from which elements will be copied.
  
- **Return Value**: 
  The `copy` function returns the number of elements copied, which can be less than the length of `src` or `dst` if one slice is shorter than the other.

### Details
- The `copy` function works with slices of any type, including arrays and user-defined types.
- It performs a shallow copy of the elements. If the slice contains pointers or references, only the references are copied, not the underlying data.
- The `dst` slice must be initialized before using the `copy` function; otherwise, a runtime panic will occur.
- It effectively handles nil slices; if `src` or `dst` is nil, the function will return 0 without causing an error.

## Examples

### Basic Example
```go
package main

import "fmt"

func main() {
    src := []int{1, 2, 3, 4, 5}
    dst := make([]int, 3) // Destination slice with length 3

    n := copy(dst, src) // Copy data from src to dst
    fmt.Println(dst)    // Output: [1 2 3]
    fmt.Println(n)      // Output: 3 (number of elements copied)
}
```

### Example with Larger Source
```go
package main

import "fmt"

func main() {
    src := []string{"a", "b", "c", "d"}
    dst := make([]string, 10) // Destination slice with length 10

    n := copy(dst, src) // Copy data from src to dst
    fmt.Println(dst)    // Output: [a b c d  ]
    fmt.Println(n)      // Output: 4 (number of elements copied)
}
```

### Example with Nil Slice
```go
package main

import "fmt"

func main() {
    var src []int // nil slice
    dst := make([]int, 5)

    n := copy(dst, src) // Copy from nil slice
    fmt.Println(dst)    // Output: [0 0 0 0 0]
    fmt.Println(n)      // Output: 0 (no elements copied)
}
```

## Explanation
When using the `copy` function, it is important to remember that:
- The function does not check if the slices have the same type; mismatched types will result in a compilation error.
- If `dst` is smaller than `src`, only the first `len(dst)` elements are copied.
- If `src` is smaller than `dst`, only the first `len(src)` elements will be copied, and the remaining elements in `dst` will remain unchanged.
- Always ensure that `dst` is allocated with sufficient length to avoid runtime panics.

## One Line Summary
The `copy` function in Go efficiently duplicates elements from one slice to another while handling various scenarios, such as nil slices and differing lengths.