<!--
Meta Description: # Go 語言中的 "case" 語句：使用指南與範例 ## 摘要 「case」語句是 Go 語言中的一種控制結構，用於實現多路分支選擇，可用來替代傳統的 if-else 結構。 ## 文檔 在 Go 語言中，「case」語句通常與「switch」語句結合使用，允許根據不同的條件執行不同的程式碼塊。...
Meta Keywords: case, fmt, switch, println, fallthrough
-->

# Go 語言中的 "case" 語句：使用指南與範例

## 摘要
「case」語句是 Go 語言中的一種控制結構，用於實現多路分支選擇，可用來替代傳統的 if-else 結構。

## 文檔
在 Go 語言中，「case」語句通常與「switch」語句結合使用，允許根據不同的條件執行不同的程式碼塊。這樣的結構使得程式碼更加清晰和易於維護。

### 目的
使用「case」語句的主要目的是提高程式碼的可讀性和可維護性，特別是在需要根據多個條件執行不同邏輯的情況下。

### 用法
「case」語句通常在「switch」結構內部使用，語法如下：

```go
switch <expression> {
case <value1>:
    // 當 <expression> == <value1> 時執行的程式碼
case <value2>:
    // 當 <expression> == <value2> 時執行的程式碼
default:
    // 當 <expression> 不符合任何 case 的時候執行的程式碼
}
```

### 詳細說明
- **表達式**：在 switch 語句中，表達式的值將與各個 case 的值進行比較。
- **多個值**：一個 case 可以接受多個值，使用逗號分隔。
- **fallthrough**：如果希望在某個 case 完成後繼續執行下一個 case，可以使用 fallthrough 關鍵字。

## 範例
以下是一些「case」語句的基本使用範例：

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
        fmt.Println("未知的日子")
    }
}
```

### 使用 fallthrough
```go
package main

import "fmt"

func main() {
    number := 2

    switch number {
    case 1:
        fmt.Println("一")
        fallthrough
    case 2:
        fmt.Println("二")
        fallthrough
    case 3:
        fmt.Println("三")
    default:
        fmt.Println("未知數字")
    }
}
```

## 解釋
在使用「case」語句時，開發者應注意以下幾點：
- **可讀性**：即使「switch」語句在功能上類似多重「if」語句，但當有許多條件時，使用「switch」能提升程式碼的可讀性。
- **fallthrough 的使用**：在使用 fallthrough 時要小心，因為這會導致執行下一個 case 的程式碼，即使當前 case 的條件不再符合。
- **不支持條件的 case**：Go 的 case 必須是常數值，不能是變量或表達式。

## 一句總結
「case」語句是 Go 語言中用於實現多路分支邏輯的重要工具，有助於提高程式碼的結構性與可讀性。