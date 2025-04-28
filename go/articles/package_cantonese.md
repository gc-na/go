<!--
Meta Description: # Go 語言中的「package」：結構與使用 ## 概述 在 Go 語言中，「package」是組織和管理代碼的基本單位。它允許開發者將代碼分成可重用和可維護的模塊，並促進代碼的清晰性和重用性。 ## 文檔 ### 目的 在 Go 中，使用 package 的主要目的是將相關的代碼集中在一起，方...
Meta Keywords: package, mathutil, fmt, main, mypackage
-->

# Go 語言中的「package」：結構與使用

## 概述
在 Go 語言中，「package」是組織和管理代碼的基本單位。它允許開發者將代碼分成可重用和可維護的模塊，並促進代碼的清晰性和重用性。

## 文檔
### 目的
在 Go 中，使用 package 的主要目的是將相關的代碼集中在一起，方便管理和分發。每個 Go 檔案都屬於一個 package，這有助於結構化大型應用程序。

### 使用
要創建一個 package，首先需要在 Go 檔案的開頭使用 `package` 關鍵字來定義 package 名稱。然後，可以在這個 package 中定義變量、函數、類型等。以下是基本的 package 結構：

```go
package mypackage

import "fmt"

// 函數範例
func Hello() {
    fmt.Println("你好，世界！")
}
```

在使用其他 package 時，可以使用 `import` 語句來引入所需的 package，例如：

```go
package main

import (
    "fmt"
    "mypackage" // 引入自定義 package
)

func main() {
    mypackage.Hello() // 調用 mypackage 中的 Hello 函數
}
```

### 詳細信息
- **命名規則**：package 名稱應該簡短且具有描述性，通常使用小寫字母，避免使用底線和大寫字母。
- **導出標識符**：以大寫字母開頭的變量和函數是可導出的，這意味著其他 package 可以訪問它們。
- **隱私性**：以小寫字母開頭的標識符是私有的，僅能在定義它們的 package 中訪問。

## 範例
### 創建一個簡單的 package

1. 創建一個名為 `mathutil` 的 package：

```go
// mathutil.go
package mathutil

func Add(a int, b int) int {
    return a + b
}
```

2. 在主應用程序中使用 `mathutil`：

```go
// main.go
package main

import (
    "fmt"
    "mathutil"
)

func main() {
    result := mathutil.Add(3, 5)
    fmt.Println(result) // 8
}
```

## 說明
- **常見問題**：確保在同一目錄下使用相同的 package 名稱，否則會導致編譯錯誤。
- **路徑問題**：在導入 package 時，請確保路徑正確，特別是在使用 Go Modules 時。
- **循環導入**：避免兩個 package 之間的循環導入，這會導致編譯錯誤。

## 總結
在 Go 語言中，package 是一個關鍵概念，提供了代碼組織和重用的能力。