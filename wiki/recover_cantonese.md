<!--
Meta Description: # Go 語言中的 recover：錯誤處理的利器 ## 簡介 `recover` 是 Go 語言中一個重要的內建函數，主要用於捕獲因為恐慌（panic）而導致的程序崩潰，從而讓程式能夠優雅地恢復運行。這個功能在錯誤處理和異常管理中扮演著關鍵角色。 ## 文檔 ### 目的 `recover` 主要...
Meta Keywords: recover, panic, fmt, println, nil
-->

# Go 語言中的 recover：錯誤處理的利器

## 簡介
`recover` 是 Go 語言中一個重要的內建函數，主要用於捕獲因為恐慌（panic）而導致的程序崩潰，從而讓程式能夠優雅地恢復運行。這個功能在錯誤處理和異常管理中扮演著關鍵角色。

## 文檔
### 目的
`recover` 主要用於從恐慌狀態中恢復控制，防止程序因未處理的錯誤而終止。

### 用法
`recover` 只能在延遲調用的函數（deferred function）中使用。當調用 `recover` 時，如果程序當前處於恐慌狀態，它將返回當前的恐慌值；如果沒有恐慌發生，則返回 `nil`。

### 詳情
- 在使用 `recover` 時，需確保它在延遲調用的函數中。
- 使用 `recover` 可以擷取到引發恐慌的具體錯誤資訊，並進行相應的處理。
- `recover` 只在同一 goroutine 中有效，無法跨 goroutine 使用。

## 示例
### 基本用法示例
以下是一個使用 `recover` 的簡單示例：

```go
package main

import (
    "fmt"
)

func main() {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Recovered from:", r)
        }
    }()

    fmt.Println("Before panic")
    panic("Something went wrong!")
    fmt.Println("After panic") // 這行不會被執行
}
```

在這個示例中，當 `panic` 發生時，`recover` 將捕獲到錯誤並輸出相關信息，程序不會異常終止。

## 解釋
- **常見陷阱**：如果 `recover` 不在延遲函數中調用，則無法正確捕獲到恐慌狀態。
- **額外注意**：在使用 `recover` 時，應謹慎處理捕獲的錯誤，避免隱藏潛在的問題。
- **不建議過度使用**：雖然 `recover` 是一個強大的工具，但不應該用來替代正常的錯誤處理流程。

## 一行總結
`recover` 是 Go 語言中用於捕獲恐慌並恢復程序運行的內建函數。