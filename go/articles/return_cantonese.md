<!--
Meta Description: # Go 語言中的「return」關鍵字：用途與示例 ## 概述 「return」是 Go 語言中用於結束函數執行並返回值的關鍵字，是函數編程的重要組成部分。 ## 文檔 ### 目的 「return」關鍵字用於從函數返回結果，並且可以選擇性地返回多個值。每個函數都可以指定返回值的類型，並且在函數結...
Meta Keywords: return, int, func, result, main
-->

# Go 語言中的「return」關鍵字：用途與示例

## 概述
「return」是 Go 語言中用於結束函數執行並返回值的關鍵字，是函數編程的重要組成部分。

## 文檔
### 目的
「return」關鍵字用於從函數返回結果，並且可以選擇性地返回多個值。每個函數都可以指定返回值的類型，並且在函數結尾使用「return」來將計算結果返回給調用者。

### 使用方法
在 Go 中，函數的定義可以包括返回值類型的聲明。若要返回值，必須使用「return」關鍵字，後面跟上要返回的變量或表達式。

語法範例：
```go
func 函數名稱(參數類型) 返回類型 {
    // 函數主體
    return 返回值
}
```

如果函數有多個返回值，則可以使用逗號分隔返回值：
```go
func 函數名稱(參數類型) (返回類型1, 返回類型2) {
    // 函數主體
    return 返回值1, 返回值2
}
```

## 示例
### 單一返回值
```go
package main

import "fmt"

func add(a int, b int) int {
    return a + b
}

func main() {
    result := add(2, 3)
    fmt.Println(result) // 輸出：5
}
```

### 多重返回值
```go
package main

import "fmt"

func divide(a int, b int) (int, int) {
    return a / b, a % b
}

func main() {
    quotient, remainder := divide(10, 3)
    fmt.Println(quotient, remainder) // 輸出：3 1
}
```

## 解釋
在使用「return」時，開發者需要注意以下幾點：

1. **返回類型一致性**：返回值必須與函數定義中聲明的返回類型一致。
2. **所有路徑均需返回值**：在 Go 中，若函數聲明了返回值類型，則必須在所有執行路徑中都使用「return」返回值。
3. **命名返回值**：可以在函數定義中為返回值命名，這樣可以省略「return」後的變量，如下所示：

   ```go
   func namedReturn() (result int) {
       result = 42
       return // 等同於 return result
   }
   ```

4. **延遲返回**：在使用「defer」語句時，返回值可以在函數結束前被修改。

## 一句總結
「return」關鍵字是 Go 語言中結束函數並返回結果的關鍵，支持單個或多個返回值。