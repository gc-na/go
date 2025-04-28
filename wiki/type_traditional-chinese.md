<!--
Meta Description: # Go 語言中的 "type"：類型定義與使用 ## 簡介 在 Go 語言中，`type` 關鍵字用於定義新的資料型別，這使得程式設計師可以創建自定義的資料結構並提高程式碼的可讀性和可維護性。 ## 文檔 `type` 關鍵字的主要目的是為了創建新的型別，這可以是結構體、介面、函數類型、或是基本型...
Meta Keywords: type, int, func, main, fmt
-->

# Go 語言中的 "type"：類型定義與使用

## 簡介
在 Go 語言中，`type` 關鍵字用於定義新的資料型別，這使得程式設計師可以創建自定義的資料結構並提高程式碼的可讀性和可維護性。

## 文檔
`type` 關鍵字的主要目的是為了創建新的型別，這可以是結構體、介面、函數類型、或是基本型別的別名。使用 `type` 可以讓開發者更清楚地表達資料的結構和意圖。

### 用法
在 Go 中，`type` 的基本語法如下：

```go
type TypeName BaseType
```

- `TypeName` 是你所定義的新型別名稱。
- `BaseType` 是你希望擴展或基於的資料型別。

### 詳細說明
- **結構體**（Structs）：`type` 常用於定義結構體，例如：
  ```go
  type Person struct {
      Name string
      Age  int
  }
  ```

- **介面**（Interfaces）：可以使用 `type` 定義介面，這是 Go 中實現多型的一種方式：
  ```go
  type Speaker interface {
      Speak() string
  }
  ```

- **函數類型**：你也可以定義函數類型，例如：
  ```go
  type MathFunc func(int, int) int
  ```

- **基本型別別名**：`type` 也可以用來為現有的型別創建別名：
  ```go
  type MyInt int
  ```

## 範例
以下是使用 `type` 定義自定義型別的基本範例：

### 結構體範例
```go
package main

import "fmt"

type Person struct {
    Name string
    Age  int
}

func main() {
    p := Person{Name: "Alice", Age: 30}
    fmt.Println(p)
}
```

### 介面範例
```go
package main

import "fmt"

type Speaker interface {
    Speak() string
}

type Dog struct{}

func (d Dog) Speak() string {
    return "汪汪"
}

func main() {
    var s Speaker = Dog{}
    fmt.Println(s.Speak())
}
```

### 函數類型範例
```go
package main

import "fmt"

type MathFunc func(int, int) int

func main() {
    add := func(a, b int) int {
        return a + b
    }
    
    var operation MathFunc = add
    fmt.Println(operation(2, 3))
}
```

## 說明
在使用 `type` 定義型別時，開發者需要注意以下幾點：
- **命名慣例**：自定義型別的名稱應該以大寫字母開頭，以便於在包外部使用。
- **繼承與組合**：結構體可以嵌套其他結構體，這樣可以達到組合的效果，但要注意避免過度複雜的結構。
- **介面的實現**：任何類型只要實現了介面要求的方法，就自動滿足該介面，無需顯式聲明。

## 單行總結
`type` 關鍵字在 Go 語言中用於創建自定義型別，從而提高程式碼的可讀性和維護性。