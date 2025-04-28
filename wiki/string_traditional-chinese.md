<!--
Meta Description: # Go 語言中的字串 (string) ## 摘要 在 Go 語言中，`string` 是一種基本數據類型，用於表示文本數據。它在內存中以 UTF-8 編碼的字元序列的形式存儲，並提供了多種操作和方法來處理字串。 ## 文件說明 在 Go 語言中，`string` 類型是不可變的，這意味著一旦創建...
Meta Keywords: string, fmt, greeting, str1, len
-->

# Go 語言中的字串 (string)

## 摘要
在 Go 語言中，`string` 是一種基本數據類型，用於表示文本數據。它在內存中以 UTF-8 編碼的字元序列的形式存儲，並提供了多種操作和方法來處理字串。

## 文件說明
在 Go 語言中，`string` 類型是不可變的，這意味著一旦創建，字串的內容無法被更改。字串可以通過字面量創建，也可以通過其他方法（如 `fmt.Sprintf` 或 `strings` 包中的函數）生成。

### 用法
- 字串定義：可以使用雙引號或反引號來定義字串。
  ```go
  var str1 string = "Hello, World!"
  var str2 string = `這是一個多行字串。`
  ```

- 字串長度：使用 `len()` 函數來獲取字串的長度（以字元計算）。
  ```go
  length := len(str1) // 返回 13
  ```

- 字串連接：可以使用 `+` 操作符來連接兩個字串。
  ```go
  combined := str1 + " " + str2
  ```

- 子字串：可以使用切片語法來獲取字串的子字串。
  ```go
  subStr := str1[7:12] // 返回 "World"
  ```

## 範例
以下是一些基本的字串使用範例：

```go
package main

import (
    "fmt"
)

func main() {
    // 定義字串
    greeting := "Hello, 世界!"
    fmt.Println(greeting)

    // 獲取字串長度
    fmt.Println("字串長度:", len(greeting))

    // 字串連接
    farewell := "再見!"
    message := greeting + " " + farewell
    fmt.Println(message)

    // 獲取子字串
    subStr := greeting[7:9]
    fmt.Println("子字串:", subStr)
}
```

## 解釋
在使用 Go 的字串時，有一些常見的陷阱和注意事項：

- **不可變性**：字串是不可變的，這意味著任何對字串的操作（如連接）都會創建一個新的字串，而不會修改原有字串。
  
- **UTF-8 編碼**：Go 字串以 UTF-8 編碼存儲，這意味著某些字元（特別是非 ASCII 字元）可能佔用多個字節。使用 `len()` 函數獲取的長度是字節數，而非字元數。

- **字串切片**：當使用切片語法獲取字串的子字串時，需注意索引範圍，超出範圍會導致運行時錯誤。

- **性能考量**：在需要頻繁修改字串的情況下，可以考慮使用 `strings.Builder` 來提高性能。

## 一句總結
Go 語言中的 `string` 類型是一種不可變的文本數據表示，提供了多種方法來處理和操作字串。