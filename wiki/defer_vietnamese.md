<!--
Meta Description: # Cách Sử Dụng Lệnh "defer" Trong Ngôn Ngữ Lập Trình Go ## Tóm tắt Lệnh `defer` trong Go được sử dụng để trì hoãn việc thực thi một hàm cho đến khi hà...
Meta Keywords: defer, hàm, được, thực, lệnh
-->

# Cách Sử Dụng Lệnh "defer" Trong Ngôn Ngữ Lập Trình Go

## Tóm tắt
Lệnh `defer` trong Go được sử dụng để trì hoãn việc thực thi một hàm cho đến khi hàm bao quanh nó hoàn thành. Đây là một kỹ thuật hữu ích để đảm bảo rằng các tài nguyên như tệp hoặc kết nối mạng được giải phóng đúng cách.

## Tài liệu
### Mục đích
Lệnh `defer` giúp đảm bảo rằng một hàm sẽ được gọi ngay trước khi hàm hiện tại trở về, bất kể hàm đó kết thúc thành công hay gặp lỗi.

### Cách sử dụng
Cú pháp của lệnh `defer` rất đơn giản:
```go
defer hàm()
```
Khi bạn gọi một hàm với `defer`, hàm đó sẽ không được thực thi ngay lập tức. Thay vào đó, Go sẽ lưu trữ lệnh gọi hàm đó và thực thi nó khi hàm hiện tại kết thúc.

### Chi tiết
- Các lệnh `defer` được thực hiện theo thứ tự LIFO (Last In, First Out).
- Bạn có thể sử dụng nhiều lệnh `defer` trong một hàm, và chúng sẽ được thực thi theo thứ tự ngược lại so với khi chúng được khai báo.
- `defer` rất hữu ích trong việc xử lý tài nguyên như tệp, cơ sở dữ liệu, hoặc các kết nối mạng, đảm bảo rằng chúng được đóng lại sau khi sử dụng.

## Ví dụ
### Ví dụ Cơ Bản
```go
package main

import "fmt"

func main() {
    defer fmt.Println("Hàm defer này sẽ được gọi sau khi main() kết thúc.")
    fmt.Println("Hàm main() đang chạy.")
}
```
**Kết quả:**
```
Hàm main() đang chạy.
Hàm defer này sẽ được gọi sau khi main() kết thúc.
```

### Ví dụ với Tài Nguyên
```go
package main

import (
    "fmt"
    "os"
)

func main() {
    file, err := os.Open("test.txt")
    if err != nil {
        fmt.Println(err)
        return
    }
    defer file.Close() // Đảm bảo rằng tệp sẽ được đóng

    // Thực hiện các thao tác với tệp
    fmt.Println("Đang làm việc với tệp...")
}
```

## Giải thích
### Những Cạm Bẫy Thường Gặp
- **Thứ tự thực thi:** Nhớ rằng các lệnh `defer` được thực hiện theo thứ tự ngược lại. Nếu bạn không cẩn thận, điều này có thể dẫn đến những kết quả không mong muốn.
- **Tham số:** Tham số của hàm được gọi sau lệnh `defer` sẽ được đánh giá ngay lập tức, không phải khi hàm defer được thực thi.
  
### Lưu Ý
- Không nên lạm dụng `defer` trong vòng lặp lớn, vì nó có thể dẫn đến lãng phí bộ nhớ do tạo nhiều hàm defer.
- `defer` thực sự hữu ích trong các tình huống xử lý lỗi, giúp mã dễ đọc và bảo trì hơn.

## Tóm tắt một câu
Lệnh `defer` trong Go cho phép trì hoãn việc thực thi một hàm cho đến khi hàm hiện tại hoàn thành, giúp quản lý tài nguyên hiệu quả và dễ dàng hơn.