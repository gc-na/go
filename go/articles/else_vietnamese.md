<!--
Meta Description: # Câu Lệnh "else" trong Ngôn Ngữ Lập Trình Go: Cách Sử Dụng và Ví Dụ ## Tóm tắt Câu lệnh "else" trong ngôn ngữ lập trình Go cho phép lập trình viên ch...
Meta Keywords: else, câu, lệnh, điều, một
-->

# Câu Lệnh "else" trong Ngôn Ngữ Lập Trình Go: Cách Sử Dụng và Ví Dụ

## Tóm tắt
Câu lệnh "else" trong ngôn ngữ lập trình Go cho phép lập trình viên chỉ định một khối mã sẽ được thực thi khi điều kiện trong câu lệnh "if" không thỏa mãn. Điều này cung cấp một cách để xử lý các tình huống khác nhau trong chương trình một cách hiệu quả.

## Tài liệu
Câu lệnh "else" được sử dụng kết hợp với câu lệnh "if" để điều khiển luồng thực thi của chương trình. Cú pháp cơ bản của "else" trong Go như sau:

```go
if điều_kiện {
    // mã sẽ chạy nếu điều_kiện là đúng
} else {
    // mã sẽ chạy nếu điều_kiện là sai
}
```

### Mục đích
Mục đích chính của câu lệnh "else" là để cung cấp một nhánh thay thế cho câu lệnh "if", cho phép bạn xử lý các tình huống mà điều kiện không được đáp ứng.

### Cách Sử Dụng
Câu lệnh "else" có thể được sử dụng độc lập hoặc kết hợp với câu lệnh "else if" để kiểm tra nhiều điều kiện. Cú pháp mở rộng như sau:

```go
if điều_kiện1 {
    // mã khi điều_kiện1 là đúng
} else if điều_kiện2 {
    // mã khi điều_kiện2 là đúng
} else {
    // mã khi tất cả các điều kiện trên đều sai
}
```

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng câu lệnh "else":

### Ví dụ 1: Sử dụng đơn giản
```go
package main

import "fmt"

func main() {
    số := 10
    if số%2 == 0 {
        fmt.Println("Số là chẵn")
    } else {
        fmt.Println("Số là lẻ")
    }
}
```

### Ví dụ 2: Sử dụng với else if
```go
package main

import "fmt"

func main() {
    điểm := 85
    if điểm >= 90 {
        fmt.Println("Xuất sắc")
    } else if điểm >= 75 {
        fmt.Println("Khá")
    } else {
        fmt.Println("Cần cải thiện")
    }
}
```

## Giải Thích
Khi sử dụng câu lệnh "else", cần lưu ý một số điều sau:

- **Quy tắc thụt lề**: Trong Go, việc thụt lề là rất quan trọng. Phải đảm bảo rằng các khối mã được thụt lề đúng cách để tránh lỗi biên dịch.
- **Câu lệnh không bắt buộc**: Câu lệnh "else" không phải là bắt buộc. Nếu bạn chỉ cần kiểm tra một điều kiện duy nhất, bạn có thể chỉ sử dụng câu lệnh "if".
- **Nhiều điều kiện**: Bạn có thể kết hợp nhiều câu lệnh "else if" để kiểm tra nhiều điều kiện khác nhau, nhưng cần nhớ rằng chỉ một khối mã sẽ được thực thi.

## Tóm tắt một dòng
Câu lệnh "else" trong Go cho phép lập trình viên xử lý các tình huống khi điều kiện trong câu lệnh "if" không được đáp ứng, giúp điều khiển luồng thực thi của chương trình một cách linh hoạt.