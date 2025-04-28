<!--
Meta Description: # int64 trong Go: Kiểu dữ liệu số nguyên 64-bit ## Tóm tắt `int64` là một kiểu dữ liệu trong ngôn ngữ lập trình Go, được sử dụng để biểu diễn các số n...
Meta Keywords: int64, các, liệu, trong, kiểu
-->

# int64 trong Go: Kiểu dữ liệu số nguyên 64-bit

## Tóm tắt
`int64` là một kiểu dữ liệu trong ngôn ngữ lập trình Go, được sử dụng để biểu diễn các số nguyên 64-bit, cho phép lưu trữ các giá trị số lớn hơn nhiều so với các kiểu dữ liệu số nguyên khác như `int` hay `int32`. Kiểu dữ liệu này rất hữu ích trong các ứng dụng yêu cầu xử lý số lượng lớn dữ liệu hoặc khi cần tính toán các giá trị vượt quá giới hạn của các kiểu số nguyên nhỏ hơn.

## Tài liệu
### Mục đích
`int64` là một phần của gói `builtin` trong Go, chứa các kiểu dữ liệu cơ bản. Kiểu này được thiết kế để lưu trữ các số nguyên trong phạm vi từ -9,223,372,036,854,775,808 đến 9,223,372,036,854,775,807. Đây là một lựa chọn lý tưởng cho các ứng dụng cần xử lý các số nguyên lớn hoặc khi bạn cần tính toán chính xác trong các lĩnh vực như tài chính, khoa học dữ liệu và lập trình hệ thống.

### Cách sử dụng
Để sử dụng kiểu dữ liệu `int64`, bạn có thể khai báo biến như sau:

```go
var number int64
```

Hoặc bạn có thể khai báo và khởi tạo biến cùng một lúc:

```go
number := int64(100)
```

### Chi tiết
- `int64` là một trong nhiều kiểu số nguyên trong Go, bên cạnh `int`, `int8`, `int16`, `int32` và `uint64`.
- Trong Go, kích thước của `int` có thể thay đổi tùy thuộc vào nền tảng (32-bit hoặc 64-bit), trong khi `int64` luôn có kích thước 64-bit.
- Việc sử dụng `int64` giúp tránh các lỗi tràn số (overflow) khi làm việc với các phép toán số lớn.

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng `int64` trong Go:

### Ví dụ 1: Khai báo và khởi tạo
```go
package main

import "fmt"

func main() {
    var a int64 = 9223372036854775807
    fmt.Println("Giá trị của a:", a)
}
```

### Ví dụ 2: Phép toán
```go
package main

import "fmt"

func main() {
    var x int64 = 1000000
    var y int64 = 2000000
    var sum int64 = x + y
    fmt.Println("Tổng của x và y:", sum)
}
```

### Ví dụ 3: Sử dụng với các hàm
```go
package main

import "fmt"

func doubleValue(value int64) int64 {
    return value * 2
}

func main() {
    var num int64 = 10
    fmt.Println("Giá trị gấp đôi của num:", doubleValue(num))
}
```

## Giải thích
Mặc dù `int64` rất mạnh mẽ, nhưng có một số điều cần lưu ý:
- Nếu bạn không cẩn thận, có thể xảy ra các lỗi tràn số nếu bạn thực hiện các phép toán mà vượt quá giới hạn của kiểu dữ liệu này.
- Khi chuyển đổi giữa các kiểu dữ liệu số khác nhau, bạn cần phải chú ý đến các vấn đề về loại dữ liệu và khả năng xảy ra lỗi.

## Tóm tắt một dòng
`int64` trong Go là kiểu dữ liệu số nguyên 64-bit, cho phép lưu trữ và xử lý các giá trị số lớn một cách an toàn và hiệu quả.