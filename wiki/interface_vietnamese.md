<!--
Meta Description: # Giao diện trong Go: Cách sử dụng và ứng dụng ## Tóm tắt Giao diện (interface) trong ngôn ngữ lập trình Go cho phép định nghĩa các phương thức mà một...
Meta Keywords: diện, giao, kiểu, các, phương
-->

# Giao diện trong Go: Cách sử dụng và ứng dụng

## Tóm tắt
Giao diện (interface) trong ngôn ngữ lập trình Go cho phép định nghĩa các phương thức mà một kiểu dữ liệu phải triển khai, tạo điều kiện thuận lợi cho việc trừu tượng hóa và xây dựng mã linh hoạt hơn.

## Tài liệu
Giao diện trong Go là một tập hợp các phương thức mà các kiểu dữ liệu có thể triển khai. Giao diện không chứa bất kỳ hiện thực hóa nào; thay vào đó, nó chỉ định nghĩa hành vi mà một kiểu phải có. Điều này cho phép xây dựng các chương trình linh hoạt và dễ bảo trì, vì bạn có thể thay thế các kiểu khác nhau mà không cần thay đổi mã sử dụng giao diện.

### Đặc điểm chính:
- **Trừu tượng hóa**: Giao diện giúp giấu đi các chi tiết cụ thể của các kiểu dữ liệu, chỉ tập trung vào hành vi.
- **Đa hình**: Các kiểu khác nhau có thể được sử dụng thay thế cho nhau nếu chúng đều triển khai cùng một giao diện.
- **Tự động**: Trong Go, một kiểu tự động được coi là triển khai một giao diện nếu nó có tất cả các phương thức được định nghĩa trong giao diện đó.

### Cú pháp:
```go
type TênGiaoDiện interface {
    PhươngThức1()
    PhươngThức2(param T) T
}
```

## Ví dụ
### Ví dụ 1: Định nghĩa và sử dụng giao diện
```go
package main

import "fmt"

// Định nghĩa giao diện
type Hinh interface {
    DienTich() float64
}

// Kiểu hình tròn
type HinhTron struct {
    BanKinh float64
}

// Cài đặt phương thức DienTich cho HinhTron
func (h HinhTron) DienTich() float64 {
    return 3.14 * h.BanKinh * h.BanKinh
}

// Kiểu hình chữ nhật
type HinhChuNhat struct {
    Dai, Rong float64
}

// Cài đặt phương thức DienTich cho HinhChuNhat
func (h HinhChuNhat) DienTich() float64 {
    return h.Dai * h.Rong
}

func main() {
    var h Hinh

    h = HinhTron{BanKinh: 5}
    fmt.Println("Diện tích hình tròn:", h.DienTich())

    h = HinhChuNhat{Dai: 4, Rong: 6}
    fmt.Println("Diện tích hình chữ nhật:", h.DienTich())
}
```

### Ví dụ 2: Sử dụng giao diện với nhiều kiểu
```go
package main

import "fmt"

// Giao diện
type ĐộngVật interface {
    Kêu() string
}

// Kiểu chó
type Chó struct{}

func (c Chó) Kêu() string {
    return "Gâu gâu"
}

// Kiểu mèo
type Mèo struct{}

func (m Mèo) Kêu() string {
    return "Meo meo"
}

func ngheKêu(d ĐộngVật) {
    fmt.Println(d.Kêu())
}

func main() {
    var d ĐộngVật

    d = Chó{}
    ngheKêu(d)

    d = Mèo{}
    ngheKêu(d)
}
```

## Giải thích
### Những điều cần lưu ý:
- **Không có từ khóa `implements`**: Trong Go, một kiểu tự động được coi là triển khai một giao diện nếu nó có tất cả các phương thức được định nghĩa trong giao diện đó, không cần khai báo rõ ràng.
- **Giao diện rỗng**: Giao diện `interface{}` (giao diện rỗng) có thể chứa bất kỳ kiểu dữ liệu nào, nhưng nên sử dụng cẩn thận vì nó có thể làm mất đi tính an toàn kiểu.
- **Tránh lỗi khi gọi phương thức**: Khi sử dụng giao diện, hãy đảm bảo rằng kiểu dữ liệu thực sự triển khai tất cả các phương thức của giao diện để tránh panic khi gọi phương thức.

## Tóm tắt một câu
Giao diện trong Go định nghĩa các hành vi mà các kiểu dữ liệu cần triển khai, giúp tạo ra mã linh hoạt và dễ bảo trì.