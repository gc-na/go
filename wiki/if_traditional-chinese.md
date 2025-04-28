<!--
Meta Description: # Go 語言中的「if」條件語句：用法與示例 ## 摘要 「if」是 Go 語言中用於控制程式流程的基本條件語句，允許根據布林條件的真偽來執行不同的程式碼區塊。 ## 文檔 在 Go 語言中，「if」語句用於執行基於條件的程式碼。它的基本語法如下： ```go if 條件 { // 當條件為真時執...
Meta Keywords: fmt, else, main, println, package
-->

# Go 語言中的「if」條件語句：用法與示例

## 摘要
「if」是 Go 語言中用於控制程式流程的基本條件語句，允許根據布林條件的真偽來執行不同的程式碼區塊。

## 文檔
在 Go 語言中，「if」語句用於執行基於條件的程式碼。它的基本語法如下：

```go
if 條件 {
    // 當條件為真時執行的程式碼
}
```

### 使用目的
「if」語句的主要目的是在程式執行過程中根據特定條件來決定執行哪一部分程式碼，這使得程式能夠根據不同的輸入或狀態作出靈活反應。

### 詳細用法
除了基本用法外，Go 的「if」語句還支持以下功能：
1. **else 語句**：可以用來在條件為假時執行其他程式碼。
2. **else if 語句**：允許對多個條件進行鏈接檢查。
3. **初始化語句**：在「if」語句中可以聲明變數，這些變數的範圍限於這個「if」語句的區塊內。

語法範例：

```go
if 初始化語句; 條件 {
    // 當條件為真時執行的程式碼
} else if 其他條件 {
    // 當其他條件為真時執行的程式碼
} else {
    // 當所有條件都為假時執行的程式碼
}
```

## 示例
以下是一些「if」語句的基本用法示例：

### 基本用法
```go
package main

import "fmt"

func main() {
    x := 10
    if x > 5 {
        fmt.Println("x 大於 5")
    }
}
```

### 使用 else
```go
package main

import "fmt"

func main() {
    x := 3
    if x > 5 {
        fmt.Println("x 大於 5")
    } else {
        fmt.Println("x 不大於 5")
    }
}
```

### 使用 else if
```go
package main

import "fmt"

func main() {
    x := 5
    if x > 5 {
        fmt.Println("x 大於 5")
    } else if x == 5 {
        fmt.Println("x 等於 5")
    } else {
        fmt.Println("x 小於 5")
    }
}
```

### 初始化語句
```go
package main

import "fmt"

func main() {
    if x := 10; x > 5 {
        fmt.Println("x 大於 5")
    }
    // fmt.Println(x) // 這將會報錯，因為 x 的作用域僅限於 if 區塊內
}
```

## 解釋
使用「if」語句時需注意以下幾點：
1. **作用域**：在「if」語句中聲明的變數只在該語句的範圍內有效。
2. **布林表達式**：條件必須返回布林值，否則將導致編譯錯誤。
3. **多條件**：使用 `else if` 和 `else` 來處理多個條件時，應注意條件的優先順序。

## 一句總結
「if」語句是 Go 語言中用於根據布林條件控制程式碼執行流程的基本結構。