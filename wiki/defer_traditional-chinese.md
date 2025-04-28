<!--
Meta Description: # Go 語言中的 defer：延遲執行的技巧 ## 摘要 `defer` 是 Go 語言中的一個關鍵字，用於延遲函數的執行，直到封閉函數返回時執行。這使得資源管理、錯誤處理和清理工作變得更加便捷。 ## 文檔 在 Go 語言中，`defer` 關鍵字可以用來註冊一個函數，該函數會在當前函數執行完畢...
Meta Keywords: defer, main, time, fmt, func
-->

# Go 語言中的 defer：延遲執行的技巧

## 摘要
`defer` 是 Go 語言中的一個關鍵字，用於延遲函數的執行，直到封閉函數返回時執行。這使得資源管理、錯誤處理和清理工作變得更加便捷。

## 文檔
在 Go 語言中，`defer` 關鍵字可以用來註冊一個函數，該函數會在當前函數執行完畢後被調用。這對於確保某些操作（例如資源釋放或清理）在函數結束時執行非常有用。

### 用途
- **資源管理**：如檔案或網路連接的關閉。
- **錯誤處理**：確保在出現錯誤時仍然能夠執行一些必要的清理操作。
- **簡化代碼**：減少重複的清理代碼，讓主邏輯更為清晰。

### 使用方式
`defer` 會在函數調用時立即評估參數，但會等到封閉函數返回時才執行。多個 `defer` 語句會按照後進先出（LIFO）的順序執行。

## 範例
以下是一些基本的 `defer` 用法示例：

### 範例 1：關閉文件
```go
package main

import (
	"fmt"
	"os"
)

func main() {
	file, err := os.Open("example.txt")
	if err != nil {
		fmt.Println(err)
		return
	}
	defer file.Close() // 確保在 main 返回之前關閉文件

	// 進行文件操作
}
```

### 範例 2：計時函數執行時間
```go
package main

import (
	"fmt"
	"time"
)

func timedFunction() {
	start := time.Now()
	defer func() {
		fmt.Printf("執行時間: %v\n", time.Since(start))
	}()

	// 模擬一些計算
	time.Sleep(2 * time.Second)
}

func main() {
	timedFunction()
}
```

## 解釋
使用 `defer` 時需要注意以下幾點：
- **參數評估**：`defer` 中的函數參數在註冊時被評估，而不是在執行時。因此，若用到變數，這些變數的當前值會被固定。
- **執行順序**：多個 `defer` 語句會按照 LIFO 的順序執行，這可能會影響代碼邏輯。
- **性能考量**：雖然 `defer` 提供了便利性，但在性能敏感的代碼中，頻繁使用 `defer` 可能導致性能下降。

## 單行總結
`defer` 是 Go 語言中用於延遲函數執行的關鍵字，非常適合資源管理和錯誤處理。