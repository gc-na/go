<!--
Meta Description: # Go 語言中的結構體（Struct）：定義與應用 ## 簡介 在 Go 語言中，結構體（Struct）是一種用來組合不同類型數據的數據結構，類似於其他編程語言中的類（Class）。結構體使得開發者可以創建複雜的數據結構，以便更好地組織和管理數據。 ## 文檔 結構體的主要目的是將不同類型的數據組...
Meta Keywords: string, fmt, car, struct, println
-->

# Go 語言中的結構體（Struct）：定義與應用

## 簡介
在 Go 語言中，結構體（Struct）是一種用來組合不同類型數據的數據結構，類似於其他編程語言中的類（Class）。結構體使得開發者可以創建複雜的數據結構，以便更好地組織和管理數據。

## 文檔
結構體的主要目的是將不同類型的數據組合成一個單一的實體。這使得開發者能夠更有效地處理和傳遞相關聯的數據。在 Go 中，結構體的定義和使用是非常靈活的，開發者可以根據需要為結構體添加字段。

### 結構體的定義
使用 `type` 關鍵字來定義一個結構體。每個字段都有一個名稱和類型，例如：

```go
type Person struct {
    Name   string
    Age    int
    Email  string
}
```

### 使用結構體
可以通過以下方式創建結構體的實例：

```go
p1 := Person{Name: "Alice", Age: 30, Email: "alice@example.com"}
```

結構體的字段可以通過點（`.`）操作符來訪問：

```go
fmt.Println(p1.Name) // 輸出：Alice
```

## 示例
以下是一個簡單的示例，展示如何使用結構體來定義和操作數據：

```go
package main

import (
    "fmt"
)

// 定義結構體
type Car struct {
    Make  string
    Model string
    Year  int
}

func main() {
    // 創建結構體實例
    car1 := Car{Make: "Toyota", Model: "Camry", Year: 2022}
    
    // 訪問結構體字段
    fmt.Println("Car Make:", car1.Make)
    fmt.Println("Car Model:", car1.Model)
    fmt.Println("Car Year:", car1.Year)
}
```

## 解釋
使用結構體時需要注意以下幾點：

1. **字段名大小寫**：在 Go 中，字段名首字母大寫表示該字段是導出的，這意味著它可以在其他包中訪問；而小寫的字段名則是私有的，僅在該包內可見。

2. **零值**：結構體的零值是一個所有字段都設置為其類型的零值的實例。例如，`string` 的零值是 `""`，而 `int` 的零值是 `0`。

3. **嵌套結構體**：結構體可以嵌套其他結構體，這樣可以構建更複雜的數據結構。

4. **指向結構體的指針**：為了更有效地傳遞結構體，可以使用指向結構體的指針，這樣可以避免複製整個結構體的開銷。

## 總結
結構體是 Go 語言中組織和管理數據的強大工具，允許開發者創建靈活且可擴展的數據結構。