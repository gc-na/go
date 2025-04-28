<!--
Meta Description: # Go 語言中的 switch 陳述式：用法、範例與注意事項 ## 概要 在 Go 語言中，`switch` 陳述式是一種控制結構，允許根據多個條件進行選擇，簡化了多重 `if-else` 陳述的寫法，增強了代碼的可讀性。 ## 文檔 ### 目的 `switch` 陳述式的主要目的是根據表達式的...
Meta Keywords: case, switch, fmt, println, default
-->

# Go 語言中的 switch 陳述式：用法、範例與注意事項

## 概要
在 Go 語言中，`switch` 陳述式是一種控制結構，允許根據多個條件進行選擇，簡化了多重 `if-else` 陳述的寫法，增強了代碼的可讀性。

## 文檔
### 目的
`switch` 陳述式的主要目的是根據表達式的值選擇執行的代碼塊。它可以用於整數、字串、布林值等類型，並支持多種條件的匹配。

### 用法
`switch` 的基本語法如下：

```go
switch 表達式 {
case 值1:
    // 執行代碼
case 值2:
    // 執行代碼
default:
    // 執行代碼
}
```

- **表達式**：可選的，若省略則 `switch` 將比較 `true`。
- **case**：每個 `case` 都是與表達式的值進行比較的條件。
- **default**：可選的，當沒有任何 `case` 匹配時執行的代碼塊。

### 詳細說明
- 當 `switch` 陳述式執行時，它會評估 `表達式` 的值，並依次檢查每個 `case`，直到找到匹配的條件或到達 `default`。
- 每個 `case` 之間不需要使用 `break` 陳述，因為 Go 語言會在找到匹配的 `case` 後自動結束 `switch` 陳述。
- 可同時使用多個值在一個 `case` 中，用逗號分隔。

## 範例
### 基本用法

以下是使用 `switch` 陳述式的基本範例：

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
        fmt.Println("未知的星期")
    }
}
```

### 多個條件

```go
package main

import (
    "fmt"
)

func main() {
    score := 85

    switch {
    case score >= 90:
        fmt.Println("優秀")
    case score >= 80:
        fmt.Println("良好")
    case score >= 70:
        fmt.Println("中等")
    default:
        fmt.Println("需要努力")
    }
}
```

## 說明
### 常見問題與注意事項
- **缺少 `break`**：在 Go 中，不必手動添加 `break` 陳述來防止落入下一個 `case`。這使得代碼更簡潔，但可能會導致意外的行為，特別是當你期望落入下一個 `case` 時。
- **表達式的類型**：`switch` 陳述式中使用的表達式可以是任何類型，這使得它非常靈活，但使用時需注意類型的一致性。
- **無法使用 `fallthrough`**：如果需要從一個 `case` 直接跳到下一個 `case`，可以使用 `fallthrough` 關鍵字，這在某些情況下可能會導致意外行為。

## 一行總結
Go 語言中的 `switch` 陳述式提供了一種簡潔且易於閱讀的方式來處理多條件選擇。