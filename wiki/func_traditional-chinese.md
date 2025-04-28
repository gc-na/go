<!--
Meta Description: # Go 語言中的 func：定義與使用 ## 概述 `func` 是 Go 語言中用來定義函式的關鍵字，函式是 Go 語言中組織和結構化代碼的基本單位。透過函式，開發者能夠將重複的代碼封裝起來，提高程式的可讀性與可維護性。 ## 文件說明 在 Go 語言中，`func` 允許開發者定義一個函式，該...
Meta Keywords: func, int, fmt, main, return
-->

# Go 語言中的 func：定義與使用

## 概述
`func` 是 Go 語言中用來定義函式的關鍵字，函式是 Go 語言中組織和結構化代碼的基本單位。透過函式，開發者能夠將重複的代碼封裝起來，提高程式的可讀性與可維護性。

## 文件說明
在 Go 語言中，`func` 允許開發者定義一個函式，該函式可以接收參數並返回結果。函式的定義語法如下：

```go
func 函式名稱(參數名稱 參數類型) 返回類型 {
    // 函式內容
}
```

### 用途
- 封裝邏輯：將特定的邏輯封裝到函式中，便於重複使用。
- 增強可讀性：透過函式名稱提供語意，增強代碼的可讀性。
- 減少重複：避免重複代碼，減少維護成本。

### 使用
在 Go 語言中，函式可以有多個參數和返回值，且支援可變參數與命名返回值。以下是一些基本的使用方式：

1. **無參數與返回值的函式**：
   ```go
   func sayHello() {
       fmt.Println("Hello, World!")
   }
   ```

2. **有參數的函式**：
   ```go
   func add(a int, b int) int {
       return a + b
   }
   ```

3. **有多個返回值的函式**：
   ```go
   func divide(a int, b int) (int, int) {
       return a / b, a % b
   }
   ```

## 範例
以下是一些使用 `func` 的範例：

### 範例 1：簡單函式
```go
package main

import "fmt"

func greet(name string) {
    fmt.Printf("Hello, %s!\n", name)
}

func main() {
    greet("Alice")
}
```

### 範例 2：帶有返回值的函式
```go
package main

import "fmt"

func multiply(x int, y int) int {
    return x * y
}

func main() {
    result := multiply(3, 4)
    fmt.Println("Result:", result)
}
```

### 範例 3：多返回值函式
```go
package main

import "fmt"

func getInfo() (string, int) {
    return "Go", 2023
}

func main() {
    lang, year := getInfo()
    fmt.Printf("Language: %s, Year: %d\n", lang, year)
}
```

## 解釋
在使用 `func` 定義函式時，開發者需注意以下幾點：

- **參數類型**：Go 語言中不支援函式重載，因此參數類型必須明確。
- **命名返回值**：可以在函式定義中指定返回值的名稱，這樣可以在函式內部直接使用名稱進行返回。
- **可變參數**：可以使用省略號 (`...`) 來定義可變數量的參數，這樣函式可以接收任意數量的參數。

## 一句總結
`func` 是 Go 語言中定義函式的關鍵字，能夠提高代碼的可讀性和重用性。