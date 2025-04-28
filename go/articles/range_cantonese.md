<!--
Meta Description: # Go 語言中的範圍 (range) 用法詳解 ## 簡介 在 Go 語言中，`range` 是一個強大的關鍵字，常用於迭代數組、切片、映射和通道等數據結構。它簡化了遍歷這些數據結構的過程，讓開發者能夠更高效地處理數據。 ## 文件說明 `range` 關鍵字的主要用途是遍歷數據結構中的元素。當使...
Meta Keywords: range, value, main, fmt, numbers
-->

# Go 語言中的範圍 (range) 用法詳解

## 簡介
在 Go 語言中，`range` 是一個強大的關鍵字，常用於迭代數組、切片、映射和通道等數據結構。它簡化了遍歷這些數據結構的過程，讓開發者能夠更高效地處理數據。

## 文件說明
`range` 關鍵字的主要用途是遍歷數據結構中的元素。當使用 `range` 迭代時，可以獲取當前元素的索引及其值，或者直接獲取值。這對於需要處理集合中每個元素的情況非常有用。

### 用法
`range` 可以用於以下幾種數據結構：
1. **數組和切片**:
   - 語法: `for index, value := range collection`
2. **映射**:
   - 語法: `for key, value := range map`
3. **通道**:
   - 語法: `for value := range channel`

在每種情況下，`range` 會返回不同的信息，根據數據結構的類型而異。

### 詳細說明
- **數組和切片**:
  當遍歷數組或切片時，`range` 返回當前元素的索引和該元素的值。若只需要值，可以使用 `_` 忽略索引。
  
- **映射**:
  在遍歷映射時，`range` 返回鍵和值，兩者都可以被使用或忽略。
  
- **通道**:
  當遍歷通道時，`range` 返回通道中傳遞的值，直到通道關閉。

## 例子
### 1. 數組和切片的使用示例
```go
package main

import "fmt"

func main() {
    numbers := []int{1, 2, 3, 4, 5}
    for index, value := range numbers {
        fmt.Printf("Index: %d, Value: %d\n", index, value)
    }
}
```

### 2. 映射的使用示例
```go
package main

import "fmt"

func main() {
    ages := map[string]int{"Alice": 25, "Bob": 30}
    for name, age := range ages {
        fmt.Printf("%s is %d years old\n", name, age)
    }
}
```

### 3. 通道的使用示例
```go
package main

import "fmt"

func main() {
    numbers := make(chan int)
    go func() {
        for i := 0; i < 5; i++ {
            numbers <- i
        }
        close(numbers)
    }()
    
    for value := range numbers {
        fmt.Println(value)
    }
}
```

## 解釋
使用 `range` 時需注意：
- 在迭代映射時，返回的鍵值對的順序是隨機的。
- 在遍歷通道時，務必確保通道已關閉，否則會導致死循環。
- 使用 `_` 來忽略不需要的返回值，以提高代碼的可讀性。

## 一句總結
`range` 是 Go 語言中用於便利地迭代數組、切片、映射和通道的關鍵字，使得數據處理更加簡潔高效。