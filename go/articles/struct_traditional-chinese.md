<!--
Meta Description: # Go 語言中的結構體 (struct)：全面指南 ## 簡介 在 Go 語言中，結構體（struct）是一種自定義數據類型，用於將不同類型的數據組合在一起。它被廣泛用於創建複雜數據結構，使得開發者能夠更有效地組織和管理數據。 ## 文檔 結構體是 Go 語言的核心特性之一，允許開發者定義一組屬性...
Meta Keywords: name, struct, fmt, age, person1
-->

# Go 語言中的結構體 (struct)：全面指南

## 簡介
在 Go 語言中，結構體（struct）是一種自定義數據類型，用於將不同類型的數據組合在一起。它被廣泛用於創建複雜數據結構，使得開發者能夠更有效地組織和管理數據。

## 文檔
結構體是 Go 語言的核心特性之一，允許開發者定義一組屬性（字段）來描述一個實體。結構體可以包含多種數據類型，並且可以嵌套使用，從而形成更複雜的數據結構。

### 目的
結構體的主要目的是將多個相關的數據字段組織到一起，提供一個清晰的接口來操作這些數據。這在開發大型應用時特別有用，因為它可以提高代碼的可讀性和維護性。

### 使用方法
在 Go 中，結構體的定義使用 `type` 關鍵字，並且可以使用小寫和大寫字母來控制字段的可見性。以下是結構體的基本語法：

```go
type StructName struct {
    FieldName1 FieldType1
    FieldName2 FieldType2
    // ...
}
```

## 範例
以下是結構體的基本使用範例：

```go
package main

import "fmt"

// 定義一個結構體
type Person struct {
    Name string
    Age  int
}

func main() {
    // 創建一個結構體實例
    person1 := Person{Name: "Alice", Age: 30}
    
    // 訪問結構體的字段
    fmt.Println("Name:", person1.Name)
    fmt.Println("Age:", person1.Age)
}
```

### 嵌套結構體範例

```go
package main

import "fmt"

// 定義一個地址結構體
type Address struct {
    City    string
    Country string
}

// 定義一個人結構體，包含地址
type Person struct {
    Name    string
    Age     int
    Address Address
}

func main() {
    // 創建一個結構體實例
    person1 := Person{
        Name: "Bob",
        Age:  25,
        Address: Address{
            City:    "Taipei",
            Country: "Taiwan",
        },
    }
    
    // 訪問嵌套結構體的字段
    fmt.Println("Name:", person1.Name)
    fmt.Println("City:", person1.Address.City)
}
```

## 解釋
使用結構體時，開發者應注意以下幾點：

1. **字段的可見性**：字段名如果以大寫字母開頭，表示該字段對外可見；如果以小寫字母開頭，則該字段僅在包內可見。
2. **初始化**：結構體可以使用字面量來初始化，也可以使用 `new` 函數來創建指向結構的指針。
3. **零值**：結構體的零值會自動初始化其所有字段為該類型的零值，這一特性在處理未初始化的結構體時非常有用。

## 一句總結
結構體是 Go 語言中的一種強大數據類型，用於組合多個字段以建立複雜數據結構。