<!--
Meta Description: # Số phức trong Go: Tìm hiểu về kiểu dữ liệu complex ## Tóm tắt Trong ngôn ngữ lập trình Go, kiểu dữ liệu `complex` là một loại kiểu dữ liệu cho phép ...
Meta Keywords: phức, phần, complex, kiểu, các
-->

# Số phức trong Go: Tìm hiểu về kiểu dữ liệu complex

## Tóm tắt
Trong ngôn ngữ lập trình Go, kiểu dữ liệu `complex` là một loại kiểu dữ liệu cho phép bạn làm việc với số phức. Số phức bao gồm một phần thực và một phần ảo, và được sử dụng rộng rãi trong các tính toán khoa học, kỹ thuật và đồ họa.

## Tài liệu
Kiểu dữ liệu `complex` trong Go có hai kích thước chính: `complex64` và `complex128`. `complex64` bao gồm hai giá trị `float32` cho phần thực và phần ảo, trong khi `complex128` bao gồm hai giá trị `float64`. Bạn có thể khai báo một số phức bằng cách sử dụng cú pháp `complex(x, y)`, trong đó `x` là phần thực và `y` là phần ảo.

### Khai báo
```go
var a complex64 = complex(1.0, 2.0) // Số phức với kiểu complex64
var b complex128 = complex(3.0, 4.0) // Số phức với kiểu complex128
```

### Toán tử
Bạn có thể thực hiện các phép toán như cộng, trừ, nhân, và chia trên các số phức, tương tự như các kiểu số khác trong Go. Các phép toán này trả về một số phức mới.

### Hàm tích hợp
Go cung cấp một số hàm tích hợp để làm việc với số phức, bao gồm:
- `real(z complex128)`: Trả về phần thực của số phức `z`.
- `imag(z complex128)`: Trả về phần ảo của số phức `z`.
- `cmplx.Abs(z complex128)`: Trả về độ lớn của số phức `z`.

## Ví dụ
### Khai báo và sử dụng số phức
```go
package main

import (
    "fmt"
)

func main() {
    // Khai báo số phức
    z1 := complex(1, 2) // 1 + 2i
    z2 := complex(3, 4) // 3 + 4i

    // Cộng hai số phức
    z3 := z1 + z2
    fmt.Println("Cộng:", z3) // In ra: Cộng: (4+6i)

    // Nhân hai số phức
    z4 := z1 * z2
    fmt.Println("Nhân:", z4) // In ra: Nhân: (-5+10i)

    // Lấy phần thực và phần ảo
    fmt.Println("Phần thực:", real(z1)) // In ra: Phần thực: 1
    fmt.Println("Phần ảo:", imag(z1))    // In ra: Phần ảo: 2
}
```

## Giải thích
Khi sử dụng kiểu dữ liệu `complex`, hãy lưu ý rằng:
- Kiểu `complex` không hỗ trợ so sánh trực tiếp với các toán tử như `==` hoặc `!=`. Bạn cần phải kiểm tra từng phần thực và ảo nếu bạn muốn so sánh.
- Các phép toán trên số phức có thể dẫn đến kết quả không như mong đợi nếu không hiểu rõ về hình thức số phức và các quy tắc toán học liên quan.
- Đảm bảo sử dụng đúng loại dữ liệu `complex64` hoặc `complex128` dựa trên yêu cầu về độ chính xác trong ứng dụng của bạn.

## Tóm tắt một dòng
Kiểu dữ liệu `complex` trong Go cho phép làm việc với số phức, bao gồm các phép toán và chức năng hữu ích cho các ứng dụng khoa học và kỹ thuật.