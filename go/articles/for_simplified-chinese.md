<!--
Meta Description: # Go语言中的“for”循环：用法与示例 ## 概述 “for”循环是Go语言中唯一的循环结构，用于重复执行代码块。它具有灵活的语法，可以实现多种循环形式，包括传统的计数循环和基于条件的循环。 ## 文档 在Go语言中，“for”循环的基本语法如下： ```go for 初始化; 条件; 后处理 ...
Meta Keywords: fmt, main, println, index, package
-->

# Go语言中的“for”循环：用法与示例

## 概述
“for”循环是Go语言中唯一的循环结构，用于重复执行代码块。它具有灵活的语法，可以实现多种循环形式，包括传统的计数循环和基于条件的循环。

## 文档
在Go语言中，“for”循环的基本语法如下：

```go
for 初始化; 条件; 后处理 {
    // 循环体
}
```

### 目的
“for”循环用于在满足特定条件的情况下重复执行代码，直到条件不再满足为止。它可以用于遍历数组、切片、映射、字符串等数据结构。

### 用法
1. **基本计数循环**：
   ```go
   for i := 0; i < 5; i++ {
       fmt.Println(i)
   }
   ```

2. **条件循环**：
   ```go
   i := 0
   for i < 5 {
       fmt.Println(i)
       i++
   }
   ```

3. **无限循环**：
   ```go
   for {
       // 永远执行的代码
   }
   ```

4. **范围循环**（用于遍历切片、数组、映射等）：
   ```go
   slice := []int{1, 2, 3}
   for index, value := range slice {
       fmt.Println(index, value)
   }
   ```

## 示例
以下是“for”循环在Go语言中的几个使用示例：

### 示例1：基本计数循环
```go
package main

import "fmt"

func main() {
    for i := 0; i < 5; i++ {
        fmt.Println("当前计数：", i)
    }
}
```

### 示例2：条件循环
```go
package main

import "fmt"

func main() {
    i := 0
    for i < 5 {
        fmt.Println("当前计数：", i)
        i++
    }
}
```

### 示例3：无限循环
```go
package main

import "fmt"

func main() {
    for {
        fmt.Println("这将一直打印")
        break // 加上break可以防止无限循环
    }
}
```

### 示例4：范围循环
```go
package main

import "fmt"

func main() {
    fruits := []string{"苹果", "香蕉", "樱桃"}
    for index, fruit := range fruits {
        fmt.Printf("索引：%d，水果：%s\n", index, fruit)
    }
}
```

## 解释
- **常见问题**：
  - 在使用“for”循环时，要注意循环条件的设置，以避免无限循环。
  - 当使用“range”遍历切片或数组时，注意变量的作用域。

- **注意事项**：
  - Go语言中的“for”循环不需要使用类似于其他语言的`while`或`do-while`语法。
  - 可以通过`break`和`continue`语句来控制循环的执行。

## 一句话总结
“for”循环是Go语言唯一的循环结构，灵活用于多种重复执行场景。