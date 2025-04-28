<!--
Meta Description: # Go 語言中的「var」關鍵字：變數宣告的基礎 ## 簡介 在 Go 語言中，「var」關鍵字用於宣告變數，是編程中不可或缺的一部分。透過使用「var」，開發者可以定義變數的名稱和類型，並在程式中使用它們來儲存和操作數據。 ## 文檔 ### 目的 「var」關鍵字的主要目的是用來聲明變數，這使...
Meta Keywords: var, fmt, name, age, isstudent
-->

# Go 語言中的「var」關鍵字：變數宣告的基礎

## 簡介
在 Go 語言中，「var」關鍵字用於宣告變數，是編程中不可或缺的一部分。透過使用「var」，開發者可以定義變數的名稱和類型，並在程式中使用它們來儲存和操作數據。

## 文檔
### 目的
「var」關鍵字的主要目的是用來聲明變數，這使得開發者可以在程式中儲存不同類型的數據。變數在程式執行過程中可以被修改，並在需要時被重新指定值。

### 使用方式
在 Go 語言中，使用「var」來宣告變數的基本語法如下：

```go
var variableName variableType
```

開發者可以在同一行中宣告多個變數，以逗號分隔：

```go
var var1, var2 variableType
```

如果在變數宣告時賦予初始值，則不必明確指定變數類型：

```go
var variableName = initialValue
```

### 詳細說明
- **變數類型**：Go 支援多種數據類型，包括整數（int）、浮點數（float）、布林（bool）和字串（string）等。
- **作用域**：變數的作用域取決於其宣告的位置。全局變數可以在整個包中使用，而局部變數只在其宣告的函數內有效。
- **零值**：未初始化的變數會自動被賦予其類型的零值。例如，整數的零值為 0，布林的零值為 false。

## 範例
以下是使用「var」關鍵字的基本範例：

```go
package main

import "fmt"

func main() {
    var name string = "Alice"
    var age int = 30
    var isStudent bool = false

    fmt.Println("Name:", name)
    fmt.Println("Age:", age)
    fmt.Println("Is Student:", isStudent)
}
```

在這個範例中，我們宣告了三個變數：`name`、`age`和`isStudent`，並將它們的值輸出到控制台。

## 解釋
- **常見陷阱**：
  - 忘記初始化變數：若不賦予變數初始值，它將默認為其類型的零值。
  - 變數作用域的誤解：局部變數無法在其外部訪問，這可能導致未定義的行為。
  
- **注意事項**：在 Go 中，變數命名遵循駝峰命名法（CamelCase），且應避免使用保留字作為變數名稱。

## 一句總結
「var」關鍵字是 Go 語言中用於宣告變數的重要工具，允許開發者靈活地儲存和操作數據。