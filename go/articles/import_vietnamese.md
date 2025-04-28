<!--
Meta Description: # Từ Khóa "import" trong Go: Cách Sử Dụng và Ý Nghĩa ## Tóm tắt Từ khóa `import` trong Go cho phép lập trình viên đưa vào các gói (packages) bên ngoài...
Meta Keywords: gói, dụng, import, các, trong
-->

# Từ Khóa "import" trong Go: Cách Sử Dụng và Ý Nghĩa

## Tóm tắt
Từ khóa `import` trong Go cho phép lập trình viên đưa vào các gói (packages) bên ngoài để sử dụng các chức năng, kiểu dữ liệu và biến đã được định nghĩa trong các gói đó, giúp tiết kiệm thời gian lập trình và tái sử dụng mã nguồn hiệu quả.

## Tài liệu
Từ khóa `import` là một phần quan trọng trong ngôn ngữ lập trình Go, cho phép bạn sử dụng lại mã nguồn từ các gói khác nhau. Mỗi gói có thể chứa nhiều tệp mã nguồn, và để sử dụng các chức năng hoặc kiểu dữ liệu từ một gói cụ thể, bạn cần phải khai báo gói đó trong mã nguồn của mình bằng cách sử dụng từ khóa `import`.

### Cách sử dụng
Cú pháp cơ bản để sử dụng từ khóa `import` trong Go như sau:

```go
import "path/to/package"
```

Bạn có thể nhập nhiều gói bằng cách sử dụng dấu ngoặc nhọn:

```go
import (
    "fmt"
    "math"
)
```

### Chi tiết
- **Đường dẫn gói**: Đường dẫn đến gói có thể là một đường dẫn tuyệt đối hoặc tương đối. Đường dẫn tuyệt đối thường được sử dụng khi gói nằm trong thư viện chính thức hoặc thư viện bên ngoài.
- **Gói tiêu chuẩn**: Go đi kèm với nhiều gói tiêu chuẩn như `fmt`, `os`, `net/http`,... Việc nhập các gói này cho phép bạn truy cập vào các chức năng cơ bản và tiện ích của ngôn ngữ.
- **Gói bên ngoài**: Bạn cũng có thể nhập các gói từ các thư viện bên ngoài bằng cách sử dụng `go get` để tải về và cài đặt chúng.

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng từ khóa `import`:

### Ví dụ 1: Nhập một gói tiêu chuẩn
```go
package main

import "fmt"

func main() {
    fmt.Println("Xin chào, thế giới!")
}
```

### Ví dụ 2: Nhập nhiều gói
```go
package main

import (
    "fmt"
    "math"
)

func main() {
    fmt.Println("Căn bậc hai của 16 là:", math.Sqrt(16))
}
```

### Ví dụ 3: Nhập gói bên ngoài
```go
package main

import (
    "fmt"
    "github.com/user/repo/package" // Gói bên ngoài
)

func main() {
    package.Function()
}
```

## Giải thích
Khi sử dụng từ khóa `import`, có một số điều cần lưu ý:
- **Tên gói**: Nếu tên gói trong mã nguồn không khớp với tên gói trong đường dẫn, bạn có thể chỉ định tên gói khác khi nhập bằng cú pháp: `import alias "path/to/package"`.
- **Gói không sử dụng**: Nếu bạn nhập một gói mà không sử dụng nó trong mã nguồn, trình biên dịch Go sẽ báo lỗi. Điều này giúp giữ cho mã nguồn sạch sẽ và dễ duy trì hơn.
- **Thứ tự nhập**: Thông thường, gói tiêu chuẩn được nhập trước, sau đó là các gói bên ngoài, và cuối cùng là các gói nội bộ của dự án.

## Tóm tắt một dòng
Từ khóa `import` trong Go cho phép lập trình viên sử dụng lại mã nguồn từ các gói khác nhau, giúp tối ưu hóa quá trình phát triển và duy trì mã nguồn.