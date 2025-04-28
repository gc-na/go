<!--
Meta Description: # Go 語言中的 fallthrough：用於 switch 語句的特殊特性 ## 概要 在 Go 語言中，`fallthrough` 是一個關鍵字，用於控制 `switch` 語句的執行流程。它允許在匹配到一個 case 之後，無條件地執行下一個 case 的內容，這與其他語言中的行為有所不同。...
Meta Keywords: case, fallthrough, switch, value, fmt
-->

# Go 語言中的 fallthrough：用於 switch 語句的特殊特性

## 概要
在 Go 語言中，`fallthrough` 是一個關鍵字，用於控制 `switch` 語句的執行流程。它允許在匹配到一個 case 之後，無條件地執行下一個 case 的內容，這與其他語言中的行為有所不同。

## 文檔
### 目的
`fallthrough` 的主要目的是讓開發者能夠在 `switch` 語句中進行連續的 case 執行，這在某些情況下可以使代碼更簡潔。

### 使用方法
在 Go 的 `switch` 語句中，當某個 case 被匹配時，可以使用 `fallthrough` 來自動轉向下一個 case 的執行。這是在 `case` 區塊的最後一行使用 `fallthrough` 關鍵字。例如：

```go
switch value {
case 1:
    fmt.Println("Value is 1")
    fallthrough
case 2:
    fmt.Println("Value is 2")
default:
    fmt.Println("Default case")
}
```

### 詳細說明
- `fallthrough` 僅能在 `case` 的最後一行使用，並且不會檢查下一個 case 的條件。
- 即使下一個 case 的條件不成立，`fallthrough` 仍然會執行下一個 case 的內容。
- 若沒有使用 `fallthrough`，在匹配到某個 case 後，`switch` 會自動結束，不會繼續執行其他 case。

## 示例
以下是 `fallthrough` 的基本使用示例：

```go
package main

import (
    "fmt"
)

func main() {
    value := 1

    switch value {
    case 1:
        fmt.Println("Value is 1")
        fallthrough
    case 2:
        fmt.Println("Value is 2")
    case 3:
        fmt.Println("Value is 3")
    default:
        fmt.Println("Default case")
    }
}
```
執行上述代碼後，輸出將是：
```
Value is 1
Value is 2
```

## 解釋
- **常見陷阱**：使用 `fallthrough` 時，開發者需小心，因為它會導致不預期的行為。若不想要自動執行下一個 case，應避免使用 `fallthrough`。
- **限制**：`fallthrough` 只能在 `switch` 的 `case` 中使用，不能在 `if` 之類的結構中使用。
- **代碼可讀性**：雖然 `fallthrough` 可以簡化某些情況下的代碼，但也可能降低代碼的可讀性，特別是在複雜的 `switch` 結構中。

## 一句總結
`fallthrough` 是 Go 語言中用於控制 `switch` 語句流程的關鍵字，允許無條件地執行下一個 case 的內容。