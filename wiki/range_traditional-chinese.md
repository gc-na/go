<!--
Meta Description: # Go 語言中的 `range`：遍歷數據結構的利器 ## 摘要 在 Go 語言中，`range` 是一個強大的關鍵字，用於遍歷各種數據結構，如數組、切片、地圖和通道。它能讓開發者以簡潔的方式獲取元素的索引和值，極大地提高了代碼的可讀性和效率。 ## 文檔 ### 目的 `range` 主要用於迭...
Meta Keywords: range, value, index, key, mychannel
-->

# Go 語言中的 `range`：遍歷數據結構的利器

## 摘要
在 Go 語言中，`range` 是一個強大的關鍵字，用於遍歷各種數據結構，如數組、切片、地圖和通道。它能讓開發者以簡潔的方式獲取元素的索引和值，極大地提高了代碼的可讀性和效率。

## 文檔
### 目的
`range` 主要用於迭代數據結構，無論是從數據結構中獲取值還是索引，它都能以簡單的語法完成。

### 使用方法
`range` 可以與以下數據結構一起使用：

- **數組與切片**：
  ```go
  for index, value := range collection {
      // 使用 index 和 value
  }
  ```

- **地圖**：
  ```go
  for key, value := range myMap {
      // 使用 key 和 value
  }
  ```

- **通道**：
  ```go
  for value := range myChannel {
      // 使用 value
  }
  ```

### 詳細說明
- 對於數組和切片，`range` 返回兩個值：元素的索引和元素的值。
- 對於地圖，`range` 返回鍵和值。
- 對於通道，`range` 返回通道中的值，直到通道關閉。
- 若只需要索引或值，可以使用 `_` 來忽略不需要的部分。

## 範例
### 數組與切片的例子
```go
numbers := []int{1, 2, 3, 4, 5}
for index, value := range numbers {
    fmt.Printf("Index: %d, Value: %d\n", index, value)
}
```

### 地圖的例子
```go
myMap := map[string]int{"apple": 5, "orange": 3}
for key, value := range myMap {
    fmt.Printf("Key: %s, Value: %d\n", key, value)
}
```

### 通道的例子
```go
myChannel := make(chan int)
go func() {
    for i := 0; i < 5; i++ {
        myChannel <- i
    }
    close(myChannel)
}()

for value := range myChannel {
    fmt.Println(value)
}
```

## 解釋
- **常見陷阱**：在使用 `range` 遍歷地圖時，返回的鍵值對是無序的，這是 Go 語言的設計特性。
- **注意事項**：在遍歷切片時，如果在循環內部修改了切片的長度，可能會導致迭代行為異常。
- **內存泄漏**：在使用通道時，確保關閉通道，以避免內存泄漏或無限循環。

## 總結
`range` 是 Go 語言中用於遍歷數據結構的高效工具，通過簡潔的語法提高了代碼的可讀性和維護性。