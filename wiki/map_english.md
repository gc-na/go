<!--
Meta Description: # Understanding Maps in Go: A Comprehensive Guide ## Synopsis Maps in Go are built-in data structures that associate keys with values, allowing for ef...
Meta Keywords: map, value, key, maps, type
-->

# Understanding Maps in Go: A Comprehensive Guide

## Synopsis
Maps in Go are built-in data structures that associate keys with values, allowing for efficient data retrieval and storage. They are similar to dictionaries or hash tables in other programming languages.

## Documentation
### Purpose
Maps in Go provide a powerful way to store and manage collections of data in key-value pairs. They are particularly useful for scenarios where quick lookups, inserts, and deletes are necessary. 

### Usage
A map is defined using the `map` keyword followed by the key type and value type inside square brackets. Here is the basic syntax:

```go
var m map[KeyType]ValueType
```

You can also initialize a map using the `make` function:

```go
m := make(map[KeyType]ValueType)
```

To insert a key-value pair into a map, use the following syntax:

```go
m[key] = value
```

To retrieve a value using a key, simply reference the key:

```go
value := m[key]
```

To delete a key-value pair from the map, use the `delete` function:

```go
delete(m, key)
```

### Details
- **Key Types**: The key type can be any type that is comparable, such as strings, integers, or structs.
- **Value Types**: The value type can be of any type, including other maps, slices, or even functions.
- **Zero Value**: The zero value of a map is `nil`. A nil map behaves like an empty map when reading but will cause a runtime panic if you attempt to write to it.
- **Concurrency**: Maps are not safe for concurrent use. If multiple goroutines access a map concurrently and at least one of them writes to the map, you must use synchronization mechanisms (like mutexes) to ensure safe access.

## Examples
### Basic Example

```go
package main

import "fmt"

func main() {
    // Creating a map
    ages := make(map[string]int)

    // Adding key-value pairs
    ages["Alice"] = 30
    ages["Bob"] = 25

    // Retrieving a value
    fmt.Println("Alice's age:", ages["Alice"])

    // Deleting a key-value pair
    delete(ages, "Bob")

    // Checking if a key exists
    if age, exists := ages["Bob"]; exists {
        fmt.Println("Bob's age:", age)
    } else {
        fmt.Println("Bob not found")
    }
}
```

### Example with Complex Values

```go
package main

import "fmt"

func main() {
    // Creating a map with a complex value type
    contact := make(map[string]map[string]string)

    // Adding nested maps
    contact["Alice"] = map[string]string{"phone": "123-4567", "email": "alice@example.com"}
    contact["Bob"] = map[string]string{"phone": "987-6543", "email": "bob@example.com"}

    // Accessing values
    fmt.Println("Alice's email:", contact["Alice"]["email"])
}
```

## Explanation
### Common Pitfalls
- **Nil Maps**: Attempting to write to a nil map will cause a runtime panic. Always initialize maps before use.
- **Key Existence**: When retrieving values, if a key does not exist, the zero value of the value type is returned. To check if a key exists, use the two-value assignment form (`value, exists := m[key]`).
- **Concurrent Access**: Maps are not safe for concurrent usage without proper synchronization. Use channels or mutexes to avoid race conditions.

### Gotchas
- The keys in a Go map must be of a type that can be compared. For example, functions and slices cannot be used as keys.
- The order of iteration over map keys is not guaranteed, which means that you should not rely on the order when iterating through maps.

## One Line Summary
Maps in Go are versatile data structures that store collections of key-value pairs, enabling efficient data retrieval and management.