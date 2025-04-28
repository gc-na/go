<!--
Meta Description: # Go语言中的append函数：使用指南与示例 ## 摘要 在Go语言中，`append`函数是用于向切片中添加元素的内置函数。它是处理动态数组时非常重要的工具，使得切片可以灵活地扩展。 ## 文档 `append`函数的基本语法如下： ```go func append(slice []Type...
Meta Keywords: append, nums, main, fmt, func
-->

# Go语言中的append函数：使用指南与示例

## 摘要
在Go语言中，`append`函数是用于向切片中添加元素的内置函数。它是处理动态数组时非常重要的工具，使得切片可以灵活地扩展。

## 文档
`append`函数的基本语法如下：

```go
func append(slice []Type, elements ...Type) []Type
```

### 目的
`append`的主要目的是将一个或多个元素添加到现有切片的末尾，并返回一个新的切片。如果原切片容量不足以容纳新增元素，`append`会自动分配一个新的切片，复制原切片的内容。

### 使用
- **参数**：`slice`是要扩展的切片，`elements`是要添加的一个或多个元素。
- **返回值**：返回一个新的切片，其中包含了原切片的所有元素以及新增的元素。

### 注意事项
- `append`函数可能会返回一个新的切片，因此在使用时应注意接收返回值。
- 虽然可以对切片进行多次`append`操作，但这可能会导致内存分配的效率降低，特别是在处理大量数据时。

## 示例
以下是几个使用`append`函数的基本示例：

### 示例 1：向切片添加单个元素
```go
package main

import "fmt"

func main() {
    nums := []int{1, 2, 3}
    nums = append(nums, 4)
    fmt.Println(nums) // 输出: [1 2 3 4]
}
```

### 示例 2：向切片添加多个元素
```go
package main

import "fmt"

func main() {
    nums := []int{1, 2, 3}
    nums = append(nums, 4, 5, 6)
    fmt.Println(nums) // 输出: [1 2 3 4 5 6]
}
```

### 示例 3：将一个切片的元素添加到另一个切片
```go
package main

import "fmt"

func main() {
    nums1 := []int{1, 2, 3}
    nums2 := []int{4, 5, 6}
    nums1 = append(nums1, nums2...) // 使用 ... 操作符展开切片
    fmt.Println(nums1) // 输出: [1 2 3 4 5 6]
}
```

## 说明
在使用`append`时，开发者常常会遇到一些常见的误区或注意事项：

- **切片的容量**：当切片的容量不足以容纳新元素时，`append`会创建一个新的切片并将原切片的内容复制到新切片中。开发者需要确保接收`append`的返回值，否则可能会丢失数据。
- **内存分配**：频繁使用`append`可能会导致性能下降。为了优化，可以预先分配一个大的切片，减少内存分配次数。
- **类型一致性**：`append`函数的类型参数必须一致，不能将不同类型的元素添加到同一切片中。

## 一句话总结
`append`函数是Go语言中用于动态扩展切片的重要工具，能够灵活地向切片添加单个或多个元素。