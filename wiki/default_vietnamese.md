<!--
Meta Description: # Từ Khóa "default" trong Ngôn Ngữ Lập Trình Go: Tính Năng và Cách Sử Dụng ## Tóm tắt Trong ngôn ngữ lập trình Go, từ khóa `default` được sử dụng tron...
Meta Keywords: không, default, fmt, println, trong
-->

# Từ Khóa "default" trong Ngôn Ngữ Lập Trình Go: Tính Năng và Cách Sử Dụng

## Tóm tắt
Trong ngôn ngữ lập trình Go, từ khóa `default` được sử dụng trong cấu trúc điều kiện `switch` và trong các kênh goroutine để xử lý các trường hợp không xác định. Nó cho phép lập trình viên xác định hành động mặc định khi không có trường hợp nào khác phù hợp.

## Tài liệu
### Mục đích
Từ khóa `default` giúp đơn giản hóa việc xử lý các giá trị không xác định trong các cấu trúc điều kiện. Nó cung cấp một cách để xử lý các tình huống mà không cần phải xác định rõ ràng từng trường hợp.

### Cách sử dụng
1. **Trong cấu trúc `switch`:**
   Khi sử dụng `switch`, bạn có thể thêm một nhánh `default` để định nghĩa hành động sẽ được thực hiện khi không có trường hợp nào khớp.

   ```go
   switch value {
   case 1:
       fmt.Println("Giá trị là 1")
   case 2:
       fmt.Println("Giá trị là 2")
   default:
       fmt.Println("Giá trị không xác định")
   }
   ```

2. **Trong Goroutine với kênh:**
   Khi sử dụng kênh, bạn có thể sử dụng `default` trong một cấu trúc `select` để thực hiện một tác vụ khi không có kênh nào sẵn sàng để gửi hoặc nhận dữ liệu.

   ```go
   select {
   case msg := <-ch1:
       fmt.Println("Nhận được tin nhắn từ ch1:", msg)
   case msg := <-ch2:
       fmt.Println("Nhận được tin nhắn từ ch2:", msg)
   default:
       fmt.Println("Không có tin nhắn nào")
   }
   ```

## Ví dụ
### Ví dụ 1: Cấu trúc `switch`
```go
package main

import "fmt"

func main() {
    value := 3
    switch value {
    case 1:
        fmt.Println("Giá trị là 1")
    case 2:
        fmt.Println("Giá trị là 2")
    default:
        fmt.Println("Giá trị không xác định")
    }
}
```

### Ví dụ 2: Cấu trúc `select`
```go
package main

import (
    "fmt"
    "time"
)

func main() {
    ch1 := make(chan string)
    ch2 := make(chan string)

    go func() {
        time.Sleep(1 * time.Second)
        ch1 <- "Tin nhắn từ kênh 1"
    }()

    go func() {
        time.Sleep(2 * time.Second)
        ch2 <- "Tin nhắn từ kênh 2"
    }()

    for i := 0; i < 2; i++ {
        select {
        case msg := <-ch1:
            fmt.Println(msg)
        case msg := <-ch2:
            fmt.Println(msg)
        default:
            fmt.Println("Không có tin nhắn nào")
        }
    }
}
```

## Giải thích
### Các vấn đề thường gặp
- **Sử dụng `default` mà không cần thiết:** Việc thêm nhánh `default` có thể dẫn đến việc bỏ lỡ các trường hợp cụ thể mà bạn muốn xử lý. Nên sử dụng một cách hợp lý để không làm giảm độ chính xác của chương trình.
- **Sử dụng `default` trong `select`:** Nếu không có kênh nào sẵn sàng, câu lệnh `select` sẽ chạy nhánh `default`, dẫn đến việc có thể không chờ đợi các kênh nhận được dữ liệu.

## Tóm tắt một câu
Từ khóa `default` trong Go cho phép xử lý các tình huống không xác định trong cấu trúc `switch` và `select`, giúp lập trình viên có thể dễ dàng quản lý logic điều kiện.