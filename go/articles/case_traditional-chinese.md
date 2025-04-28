<!--
Meta Description: # Go 語言中的 case 語句：完整指南 ## 摘要 在 Go 語言中，`case` 語句用於 `switch` 語句中，提供了一種簡潔的方式來實現多條件分支，使得根據變量的值執行相應代碼變得更加清晰和易於維護。 ## 文檔 `case` 語句是 Go 中 `switch` 語句的一部分，主要用...
Meta Keywords: case, switch, fmt, println, day
-->

# Go 語言中的 case 語句：完整指南

## 摘要
在 Go 語言中，`case` 語句用於 `switch` 語句中，提供了一種簡潔的方式來實現多條件分支，使得根據變量的值執行相應代碼變得更加清晰和易於維護。

## 文檔
`case` 語句是 Go 中 `switch` 語句的一部分，主要用於根據變量的值選擇執行的代碼塊。與傳統的 `if-else` 語句相比，`switch` 結構更具可讀性，特別是在需要處理多個條件時。

### 用法
在 Go 中，`switch` 語句的基本結構如下：

```go
switch variable {
case value1:
    // 當變量等於 value1 時執行的程式碼
case value2:
    // 當變量等於 value2 時執行的程式碼
default:
    // 當變量不等於任何 case 時執行的程式碼
}
```

`case` 語句可以用來匹配多個值，並且可以使用表達式進行匹配。此外，`switch` 語句允許不帶條件，這樣會默認使用 `true` 作為條件，並執行匹配的 `case`。

## 範例
以下是一個簡單的範例，展示如何使用 `case` 語句：

```go
package main

import (
    "fmt"
)

func main() {
    day := 3

    switch day {
    case 1:
        fmt.Println("今天是星期一")
    case 2:
        fmt.Println("今天是星期二")
    case 3:
        fmt.Println("今天是星期三")
    default:
        fmt.Println("今天是其他日子")
    }
}
```

在這個範例中，當 `day` 的值為 `3` 時，輸出為 "今天是星期三"。

### 使用多個 case
你也可以在一個 `case` 中列出多個匹配值：

```go
switch day {
case 1, 2, 3:
    fmt.Println("今天是週初")
case 4, 5:
    fmt.Println("今天是週末前")
default:
    fmt.Println("今天是週末")
}
```

## 解釋
在使用 `case` 語句時，開發者需要注意以下幾點：

- **類型匹配**：所有的 `case` 值必須與 `switch` 變量的類型相匹配。
- **獨特性**：每一個 `case` 應該是唯一的，重複的 `case` 將導致編譯錯誤。
- **Fallthrough 行為**：Go 的 `switch` 語句默認不會自動跳轉到下一個 `case`，你需要使用 `fallthrough` 關鍵字來強制跳轉，但這通常不建議使用，因為會導致不易理解的代碼邏輯。

## 一句話總結
`case` 語句在 Go 語言中用於 `switch` 語句中，提供了一種清晰且高效的方式來處理多條件分支。