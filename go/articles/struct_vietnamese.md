<!--
Meta Description: # Struct trong Go: Cấu trúc Dữ liệu và Cách Sử Dụng ## Tóm tắt Struct trong Go là một kiểu dữ liệu cho phép người lập trình nhóm các biến khác nhau lạ...
Meta Keywords: struct, một, trường, trong, liệu
-->

# Struct trong Go: Cấu trúc Dữ liệu và Cách Sử Dụng

## Tóm tắt
Struct trong Go là một kiểu dữ liệu cho phép người lập trình nhóm các biến khác nhau lại với nhau dưới một tên duy nhất, tạo ra một kiểu dữ liệu tùy chỉnh.

## Tài liệu
Struct trong Go được sử dụng để định nghĩa một kiểu dữ liệu phức tạp, có thể chứa nhiều trường (fields) khác nhau. Mỗi trường có thể là một kiểu dữ liệu cơ bản hoặc một struct khác. Struct là một trong những công cụ mạnh mẽ để tổ chức dữ liệu và tạo ra các đối tượng trong lập trình hướng đối tượng.

### Cách sử dụng
Để định nghĩa một struct, bạn sử dụng từ khóa `type`, theo sau là tên struct và các trường bên trong nó. Cú pháp cơ bản của một struct như sau:

```go
type TênStruct struct {
    Trường1 Kiểu
    Trường2 Kiểu
    // Thêm các trường khác nếu cần
}
```

### Ví dụ
Dưới đây là một ví dụ đơn giản về việc định nghĩa và sử dụng struct trong Go:

```go
package main

import (
    "fmt"
)

// Định nghĩa một struct tên là Người
type Nguoi struct {
    Ten   string
    Tuoi  int
}

func main() {
    // Khởi tạo một instance của struct Nguoi
    nguoi1 := Nguoi{
        Ten:  "Nguyễn Văn A",
        Tuoi: 30,
    }

    // In ra thông tin về người
    fmt.Println("Tên:", nguoi1.Ten)
    fmt.Println("Tuổi:", nguoi1.Tuoi)
}
```

## Giải thích
Khi làm việc với struct, có một số điểm cần lưu ý:

1. **Khởi tạo Struct**: Bạn có thể khởi tạo một struct bằng cách sử dụng dấu ngoặc nhọn `{}` và chỉ định giá trị cho các trường. Có thể khởi tạo mà không cần chỉ định tên trường, nhưng điều này có thể làm cho mã khó đọc hơn.

2. **Truy cập trường**: Các trường của struct có thể được truy cập bằng cách sử dụng dấu `.` (dấu chấm), ví dụ: `nguoi1.Ten`.

3. **Trường có thể là nil**: Nếu struct chứa các trường là con trỏ, bạn cần chú ý đến việc kiểm tra nil để tránh lỗi khi truy cập.

4. **Tính kế thừa**: Go không hỗ trợ kế thừa theo cách truyền thống như một số ngôn ngữ khác, nhưng bạn có thể sử dụng "thành phần" (embedding) để đưa một struct vào trong một struct khác.

5. **Giá trị vs. Con trỏ**: Struct được truyền bằng giá trị theo mặc định, điều này có nghĩa là một bản sao của struct sẽ được tạo ra khi bạn truyền nó vào hàm. Để tiết kiệm bộ nhớ hoặc khi làm việc với các struct lớn, bạn có thể truyền con trỏ đến struct.

## Tóm tắt một câu
Struct trong Go là một kiểu dữ liệu cho phép nhóm các trường khác nhau lại với nhau, tạo ra cấu trúc dữ liệu tùy chỉnh dễ dàng quản lý và sử dụng.