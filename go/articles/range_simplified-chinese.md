<!--
Meta Description: # Go语言中的range关键字详解 ## 概述 在Go语言中，`range`关键字用于迭代切片、数组、映射、字符串和通道等数据结构。它简化了循环操作，使得遍历集合中的元素变得更加简洁和易读。 ## 文档 `range`是一个用于迭代数据结构的关键字，可以与`for`循环结合使用。其主要目的是提供一...
Meta Keywords: range, main, fmt, func, package
-->

# Go语言中的range关键字详解

## 概述
在Go语言中，`range`关键字用于迭代切片、数组、映射、字符串和通道等数据结构。它简化了循环操作，使得遍历集合中的元素变得更加简洁和易读。

## 文档
`range`是一个用于迭代数据结构的关键字，可以与`for`循环结合使用。其主要目的是提供一种简便的方式来访问集合中的每个元素及其索引。使用`range`时，用户可以选择仅获取元素值、元素索引，或者两者都获取。

### 用法
- **切片和数组**: `for i, v := range slice` 可以获取切片或数组的索引和对应的值。
- **映射**: `for k, v := range m` 用于遍历映射的键值对。
- **字符串**: `for i, c := range str` 用于遍历字符串中的每个字符及其索引。
- **通道**: `for v := range ch` 用于接收通道中的值，直到通道关闭。

### 语法
```go
for index, value := range collection {
    // 使用index和value
}
```

## 示例
### 1. 遍历切片
```go
package main

import "fmt"

func main() {
    numbers := []int{1, 2, 3, 4, 5}
    for i, v := range numbers {
        fmt.Printf("索引: %d, 值: %d\n", i, v)
    }
}
```

### 2. 遍历字符串
```go
package main

import "fmt"

func main() {
    str := "Hello"
    for i, c := range str {
        fmt.Printf("索引: %d, 字符: %c\n", i, c)
    }
}
```

### 3. 遍历映射
```go
package main

import "fmt"

func main() {
    m := map[string]int{"a": 1, "b": 2, "c": 3}
    for k, v := range m {
        fmt.Printf("键: %s, 值: %d\n", k, v)
    }
}
```

### 4. 遍历通道
```go
package main

import "fmt"

func main() {
    ch := make(chan int)

    go func() {
        for i := 1; i <= 5; i++ {
            ch <- i
        }
        close(ch)
    }()

    for v := range ch {
        fmt.Println("接收到:", v)
    }
}
```

## 说明
使用`range`时，需要注意以下几点：
- 在遍历映射时，遍历的顺序是随机的，不同的执行可能会产生不同的顺序。
- 在遍历切片和数组时，如果只需要值而不需要索引，可以用`_`占位符来忽略索引，例如：`for _, v := range slice`。
- 当处理通道时，`range`会在通道关闭时自动退出循环。

## 一句总结
`range`关键字在Go语言中用于简化对切片、数组、映射、字符串和通道的迭代操作。