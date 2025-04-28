<!--
Meta Description: # Go 語言中的字串 (String) 用法全面指南 ## 摘要 在 Go 語言中，字串（string）是一種不可變的資料類型，用於表示文本數據。它是 Go 語言中最常用的資料型別之一，提供了多種操作字串的方法。 ## 文件 字串在 Go 語言中是由 UTF-8 編碼的字符序列組成，並且一旦創建後...
Meta Keywords: strings, main, fmt, hello, world
-->

# Go 語言中的字串 (String) 用法全面指南

## 摘要
在 Go 語言中，字串（string）是一種不可變的資料類型，用於表示文本數據。它是 Go 語言中最常用的資料型別之一，提供了多種操作字串的方法。

## 文件
字串在 Go 語言中是由 UTF-8 編碼的字符序列組成，並且一旦創建後便無法修改。字串的基本用途包括文本處理、數據顯示和用於資料傳輸等。Go 提供了豐富的內建函數和方法來操作字串，使開發者能夠輕鬆完成各種字串操作。

### 字串的聲明
字串可以通過雙引號或反引號來聲明：
```go
var str1 string = "Hello, World!"
var str2 string = `這是一個多行
字串範例。`
```

### 字串的操作
Go 語言提供了許多方法來操作字串，包括：
- **字串長度**：使用 `len()` 函數獲取字串的長度。
- **字串拼接**：使用 `+` 來拼接字串，或者使用 `strings.Join()` 函數。
- **字串切割**：使用 `strings.Split()` 來分割字串。
- **字串查詢**：使用 `strings.Contains()`、`strings.Index()` 等函數來查詢字串。

## 示例
以下是一些基本的字串使用範例：

### 字串長度
```go
package main

import "fmt"

func main() {
    str := "Hello, 世界"
    fmt.Println(len(str)) // 輸出字串的長度
}
```

### 字串拼接
```go
package main

import "fmt"

func main() {
    str1 := "Hello"
    str2 := "World"
    result := str1 + ", " + str2 + "!"
    fmt.Println(result) // 輸出: Hello, World!
}
```

### 字串查詢
```go
package main

import (
    "fmt"
    "strings"
)

func main() {
    str := "Hello, World!"
    fmt.Println(strings.Contains(str, "World")) // 輸出: true
}
```

## 解釋
使用字串時，開發者需要注意以下幾點：
- **不可變性**：字串一旦創建就不能被修改，任何改變字串的操作都會返回一個新的字串，而不是在原有字串上進行修改。
- **UTF-8 編碼**：Go 的字串是使用 UTF-8 編碼的，這意味著一個字元可能佔用多個字節，這在計算字串長度或切割字串時需要特別注意。
- **多行字串**：使用反引號來定義多行字串時，字串內的換行和空格會被保留。

## 一句話總結
Go 語言中的字串是一種不可變的文本資料類型，提供了多種內建函數來進行字串操作。