<!--
Meta Description: # Go 語言中的 switch 語句：使用與範例 ## 概述 在 Go 語言中，`switch` 語句是一種控制結構，用於根據表達式的值選擇性地執行不同的代碼塊。它提供了一種簡潔且易於閱讀的方式來處理多個條件，常用於取代冗長的 `if-else` 語句。 ## 文件說明 `switch` 語句的主...
Meta Keywords: case, switch, fmt, println, main
-->

# Go 語言中的 switch 語句：使用與範例

## 概述
在 Go 語言中，`switch` 語句是一種控制結構，用於根據表達式的值選擇性地執行不同的代碼塊。它提供了一種簡潔且易於閱讀的方式來處理多個條件，常用於取代冗長的 `if-else` 語句。

## 文件說明
`switch` 語句的主要目的是根據特定變量的值執行不同的代碼段。它可以用來簡化條件判斷，使得代碼更為清晰和可維護。基本語法如下：

```go
switch expression {
case value1:
    // 當 expression 等於 value1 時執行的代碼
case value2:
    // 當 expression 等於 value2 時執行的代碼
default:
    // 當沒有任何 case 匹配時執行的代碼
}
```

### 使用方法
- `switch` 可以不帶表達式，這樣它會默認對 `true` 進行匹配。
- 每個 case 都會自動結束，除非使用 `fallthrough` 語句。
- 可以使用多個條件在同一個 case 中。

## 範例
### 基本範例
```go
package main

import "fmt"

func main() {
    day := 3
    switch day {
    case 1:
        fmt.Println("星期一")
    case 2:
        fmt.Println("星期二")
    case 3:
        fmt.Println("星期三")
    default:
        fmt.Println("其他日子")
    }
}
```

### 無表達式的 switch
```go
package main

import "fmt"

func main() {
    number := 2
    switch {
    case number < 0:
        fmt.Println("負數")
    case number == 0:
        fmt.Println("零")
    case number > 0:
        fmt.Println("正數")
    }
}
```

### 使用 fallthrough
```go
package main

import "fmt"

func main() {
    letter := "A"
    switch letter {
    case "A":
        fmt.Println("這是 A")
        fallthrough
    case "B":
        fmt.Println("這是 B")
    default:
        fmt.Println("不是 A 或 B")
    }
}
```

## 解釋
在使用 `switch` 語句時，以下是一些常見的注意事項和陷阱：

1. **自動結束**：每個 case 在執行完後自動結束，除非明確使用 `fallthrough` 語句。
2. **類型匹配**：case 的值必須與 `switch` 表達式的類型相同。
3. **無法使用變量**：在 switch 的 case 中，無法使用變量來進行比較，必須使用常量或字面值。
4. **默認情況**：`default` case 是可選的，但建議在需要時使用，以處理未匹配的情況。

## 總結
Go 語言中的 `switch` 語句提供了一種高效且可讀的方式來處理多重條件判斷，使得代碼更為簡潔。