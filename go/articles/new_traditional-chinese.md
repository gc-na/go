<!--
Meta Description: # Go 語言中的 "new" 關鍵字：用途與範例 ## 摘要 在 Go 語言中，`new` 是一個用於分配內存並返回指向新分配的零值的指針的內建函數。它常用於創建結構體和其他類型的實例。 ## 文件說明 `new` 函數的主要目的是為一個指定類型的變量分配內存。當使用 `new(Type)` 時，...
Meta Keywords: new, type, make, main, fmt
-->

# Go 語言中的 "new" 關鍵字：用途與範例

## 摘要
在 Go 語言中，`new` 是一個用於分配內存並返回指向新分配的零值的指針的內建函數。它常用於創建結構體和其他類型的實例。

## 文件說明
`new` 函數的主要目的是為一個指定類型的變量分配內存。當使用 `new(Type)` 時，它會為 `Type` 類型的變量分配內存，並返回一個指向這個變量的指針。這個變量的值在分配時會被設置為該類型的零值。

### 用法
```go
ptr := new(Type)
```

- `Type`：要分配的類型。
- `ptr`：返回一個指向 `Type` 的指針。

### 詳細資訊
- `new` 的返回值是一個指向分配後的零值的指針。例如，`new(int)` 會返回一個指向整數零的指針。
- 使用 `new` 來創建的變量在作用域外仍然存在，這意味著如果你將該指針傳遞到函數中，你可以在函數外部訪問到它。
- `new` 跟 `make` 不同，`make` 用於初始化切片、映射和通道類型，而 `new` 主要用於普通的值類型。

## 範例
### 基本範例
```go
package main

import "fmt"

type Person struct {
    Name string
    Age  int
}

func main() {
    // 使用 new 創建一個 Person 結構的指針
    p := new(Person)
    
    // 設置屬性
    p.Name = "Alice"
    p.Age = 30
    
    // 輸出屬性
    fmt.Println(*p) // Output: {Alice 30}
}
```

### 使用 new 創建基本類型
```go
package main

import "fmt"

func main() {
    // 創建一個整數的指針
    numPtr := new(int)
    
    // 設置值
    *numPtr = 42
    
    // 輸出值
    fmt.Println(*numPtr) // Output: 42
}
```

## 說明
- **常見陷阱**：使用 `new` 時要注意，返回的是指針而非值本身，因此在使用時需要解引用（`*`）來獲取或設置值。
- **誤用**：有些開發者可能會誤將 `new` 和 `make` 混淆，請確保在需要初始化切片、映射或通道時使用 `make`。

## 一句總結
`new` 是 Go 語言中用於分配內存並返回指向零值的指針的內建函數。