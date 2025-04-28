<!--
Meta Description: # Từ Khóa "const" trong Ngôn Ngữ Go: Định Nghĩa và Cách Sử Dụng ## Tóm Tắt Từ khóa `const` trong ngôn ngữ lập trình Go được sử dụng để khai báo các hằ...
Meta Keywords: hằng, const, dụng, giá, trị
-->

# Từ Khóa "const" trong Ngôn Ngữ Go: Định Nghĩa và Cách Sử Dụng

## Tóm Tắt
Từ khóa `const` trong ngôn ngữ lập trình Go được sử dụng để khai báo các hằng số, cho phép lập trình viên định nghĩa các giá trị không thay đổi trong suốt quá trình thực thi của chương trình.

## Tài Liệu
Trong Go, từ khóa `const` được dùng để khai báo một hằng số, tức là một giá trị cố định không thể thay đổi sau khi đã được khởi tạo. Hằng số có thể là số, chuỗi, hoặc các kiểu dữ liệu khác. Việc sử dụng hằng số giúp cho mã nguồn trở nên rõ ràng hơn và dễ bảo trì hơn.

### Cú Pháp
Cú pháp để khai báo hằng số như sau:
```go
const tên_hằng = giá_trị
```

#### Ví dụ:
```go
const Pi = 3.14
const Greeting = "Xin chào"
```

Hằng số có thể được khai báo trong một nhóm:
```go
const (
    A = 1
    B = 2
    C = 3
)
```

### Mục Đích
- **Định Nghĩa Giá Trị Không Thay Đổi**: Sử dụng `const` để đảm bảo rằng một giá trị không bị thay đổi trong suốt chương trình.
- **Cải Thiện Tính Rõ Ràng**: Sử dụng hằng số giúp mã nguồn của bạn dễ hiểu hơn.

### Cách Sử Dụng
Hằng số có thể được sử dụng trong các biểu thức, điều kiện và bất kỳ nơi nào mà giá trị cụ thể được yêu cầu. Hằng số có thể được sử dụng cho các kiểu dữ liệu cơ bản như `int`, `float`, `string` và các kiểu dữ liệu phức tạp hơn.

## Ví dụ
Dưới đây là một ví dụ đơn giản về việc sử dụng từ khóa `const` trong một chương trình Go:

```go
package main

import "fmt"

const (
    SpeedOfLight = 299792458 // m/s
    EarthGravity = 9.81      // m/s^2
)

func main() {
    fmt.Println("Tốc độ ánh sáng:", SpeedOfLight)
    fmt.Println("Gia tốc trọng trường của Trái Đất:", EarthGravity)
}
```

## Giải Thích
Khi sử dụng hằng số, có một số điều cần lưu ý:
- **Không Thể Thay Đổi**: Giá trị của hằng số không thể bị thay đổi sau khi đã được khởi tạo, điều này có thể gây ra lỗi nếu bạn cố gắng làm như vậy.
- **Kiểu Dữ Liệu**: Hằng số không cần phải có kiểu dữ liệu rõ ràng, Go sẽ tự động xác định kiểu dữ liệu dựa trên giá trị được gán.
- **Giá Trị Mặc Định**: Nếu không cung cấp giá trị cho một hằng số, Go sẽ gán giá trị mặc định cho kiểu dữ liệu đó.

## Tóm Tắt Một Dòng
Từ khóa `const` trong Go cho phép khai báo các hằng số không thay đổi, giúp cải thiện tính rõ ràng và bảo trì của mã nguồn.