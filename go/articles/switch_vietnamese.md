<!--
Meta Description: # Cấu Trúc Lệnh switch trong Ngôn Ngữ Lập Trình Go ## Tóm tắt Lệnh `switch` trong Go là một cấu trúc điều khiển cho phép thực hiện nhiều lựa chọn khác...
Meta Keywords: case, switch, fmt, lệnh, một
-->

# Cấu Trúc Lệnh switch trong Ngôn Ngữ Lập Trình Go

## Tóm tắt
Lệnh `switch` trong Go là một cấu trúc điều khiển cho phép thực hiện nhiều lựa chọn khác nhau dựa trên giá trị của một biểu thức. Nó giúp mã nguồn trở nên rõ ràng và dễ đọc hơn so với việc sử dụng nhiều lệnh `if-else`.

## Tài liệu
Lệnh `switch` trong Go được sử dụng để kiểm tra một biểu thức và thực hiện các khối mã khác nhau tùy thuộc vào giá trị của biểu thức đó. Cú pháp cơ bản của lệnh `switch` như sau:

```go
switch <biểu thức> {
case <giá trị1>:
    // khối mã cho giá trị1
case <giá trị2>:
    // khối mã cho giá trị2
default:
    // khối mã mặc định nếu không có giá trị nào khớp
}
```

### Mục đích
Lệnh `switch` giúp lập trình viên dễ dàng quản lý và xử lý nhiều điều kiện khác nhau mà không cần phải lồng ghép nhiều lệnh `if-else`, từ đó giúp cải thiện tính rõ ràng và khả năng bảo trì của mã nguồn.

### Cách sử dụng
- **Biểu thức**: Biểu thức có thể là bất kỳ loại dữ liệu nào như số nguyên, chuỗi, hoặc kiểu dữ liệu tùy chỉnh.
- **Case**: Bạn có thể có nhiều `case` và mỗi `case` có thể kiểm tra một hoặc nhiều giá trị.
- **Default**: Nếu không có `case` nào khớp, khối mã trong phần `default` sẽ được thực hiện.

## Ví dụ
### Ví dụ 1: Lệnh switch đơn giản
```go
package main

import "fmt"

func main() {
    day := 3

    switch day {
    case 1:
        fmt.Println("Thứ Hai")
    case 2:
        fmt.Println("Thứ Ba")
    case 3:
        fmt.Println("Thứ Tư")
    default:
        fmt.Println("Ngày không hợp lệ")
    }
}
```

### Ví dụ 2: Nhiều điều kiện trong case
```go
package main

import "fmt"

func main() {
    char := 'a'

    switch char {
    case 'a', 'e', 'i', 'o', 'u':
        fmt.Println("Đây là nguyên âm")
    default:
        fmt.Println("Đây là phụ âm")
    }
}
```

### Ví dụ 3: Không cần biểu thức
```go
package main

import "fmt"

func main() {
    num := 2

    switch {
    case num < 0:
        fmt.Println("Số âm")
    case num == 0:
        fmt.Println("Số không")
    case num > 0:
        fmt.Println("Số dương")
    }
}
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng lệnh `switch` trong Go:

- **Tự động break**: Trong Go, không cần phải sử dụng câu lệnh `break` sau mỗi `case`. Mỗi `case` sẽ tự động dừng khi nó khớp.
- **Nhiều case**: Bạn có thể nhóm nhiều giá trị trong một `case` để giảm thiểu mã lặp lại.
- **Biểu thức không cần thiết**: Nếu bạn không cung cấp biểu thức cho `switch`, Go sẽ coi đó là một `switch true`, cho phép bạn kiểm tra nhiều điều kiện mà không cần chỉ định một giá trị cụ thể.

## Tóm tắt một dòng
Lệnh `switch` trong Go là một cấu trúc điều khiển mạnh mẽ cho phép thực hiện nhiều lựa chọn dựa trên giá trị của một biểu thức, giúp mã nguồn rõ ràng và dễ đọc hơn.