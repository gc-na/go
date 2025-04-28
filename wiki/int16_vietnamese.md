<!--
Meta Description: # int16 trong Go: Kiểu Dữ Liệu Số Nguyên 16-Bit ## Tóm tắt `int16` là một kiểu dữ liệu trong ngôn ngữ lập trình Go, dùng để đại diện cho số nguyên 16-...
Meta Keywords: int16, các, kiểu, trong, liệu
-->

# int16 trong Go: Kiểu Dữ Liệu Số Nguyên 16-Bit

## Tóm tắt
`int16` là một kiểu dữ liệu trong ngôn ngữ lập trình Go, dùng để đại diện cho số nguyên 16-bit. Kiểu này cho phép lưu trữ các giá trị số nguyên trong khoảng từ -32,768 đến 32,767, được sử dụng trong các tình huống cần tiết kiệm bộ nhớ hoặc khi làm việc với dữ liệu nhị phân.

## Tài liệu
### Mục đích
`int16` là một phần trong bộ các kiểu dữ liệu số nguyên của Go. Kiểu này được thiết kế để cung cấp một sự lựa chọn tối ưu cho các ứng dụng yêu cầu lưu trữ số nguyên với độ chính xác và kích thước nhỏ hơn so với các kiểu số nguyên lớn hơn như `int`, `int32`, hoặc `int64`.

### Cách sử dụng
Để sử dụng `int16` trong Go, bạn chỉ cần khai báo một biến với kiểu dữ liệu này. Dưới đây là cú pháp cơ bản:

```go
var x int16
```

Bạn có thể gán giá trị cho biến này như sau:

```go
x = 1000
```

Bên cạnh đó, bạn cũng có thể sử dụng `int16` trong các phép toán số học, so sánh và các tính năng khác của Go.

### Chi tiết
- **Kích thước**: `int16` chiếm 2 byte (16 bit) bộ nhớ.
- **Khoảng giá trị**: Từ -32,768 đến 32,767.
- **Sử dụng**: Thích hợp cho các ứng dụng nhúng, xử lý tín hiệu, và các bài toán yêu cầu độ chính xác cao nhưng không cần kích thước lớn.

## Ví dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng `int16` trong Go:

```go
package main

import (
    "fmt"
)

func main() {
    var a int16 = 30000
    var b int16 = 2000
    var sum int16 = a + b
    
    fmt.Println("Tổng:", sum) // In ra tổng
}
```

Trong ví dụ này, chúng ta khai báo hai biến `a` và `b` với kiểu `int16`, sau đó tính tổng và in ra kết quả.

## Giải thích
Khi làm việc với `int16`, có một số điều cần lưu ý:
- **Tràn số**: Nếu bạn cố gắng gán một giá trị lớn hơn 32,767 hoặc nhỏ hơn -32,768 cho biến `int16`, bạn sẽ gặp phải lỗi tràn số, dẫn đến kết quả không mong muốn.
- **Chuyển đổi kiểu**: Khi thực hiện các phép toán với các kiểu dữ liệu khác, bạn cần phải chuyển đổi kiểu dữ liệu cho phù hợp để tránh lỗi biên dịch.

## Tóm tắt một dòng
`int16` là một kiểu dữ liệu số nguyên 16-bit trong Go, cho phép lưu trữ các giá trị từ -32,768 đến 32,767, thích hợp cho các ứng dụng tiết kiệm bộ nhớ.