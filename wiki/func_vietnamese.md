<!--
Meta Description: # Hàm "func" trong Go: Cách định nghĩa và sử dụng ## Tóm tắt Hàm "func" trong Go là một từ khóa dùng để định nghĩa hàm, cho phép lập trình viên tạo ra...
Meta Keywords: hàm, trong, định, dụng, trả
-->

# Hàm "func" trong Go: Cách định nghĩa và sử dụng

## Tóm tắt
Hàm "func" trong Go là một từ khóa dùng để định nghĩa hàm, cho phép lập trình viên tạo ra các đoạn mã có thể tái sử dụng, giúp tổ chức và tối ưu hóa code.

## Tài liệu
Trong ngôn ngữ lập trình Go, từ khóa "func" được sử dụng để định nghĩa một hàm. Hàm là một khối mã thực hiện một nhiệm vụ cụ thể và có thể nhận tham số đầu vào và trả về giá trị. Việc sử dụng hàm giúp cho mã nguồn trở nên rõ ràng hơn, dễ bảo trì hơn và giảm thiểu việc lặp lại mã.

### Cú pháp
```go
func FunctionName(parameter1 Type1, parameter2 Type2) ReturnType {
    // Thân hàm
    return value
}
```

- **FunctionName**: Tên của hàm, theo quy tắc đặt tên trong Go.
- **parameter1, parameter2**: Tham số đầu vào của hàm. Có thể có nhiều tham số và mỗi tham số phải chỉ định kiểu dữ liệu.
- **ReturnType**: Kiểu dữ liệu mà hàm sẽ trả về. Nếu hàm không trả về giá trị nào, phần này có thể bỏ qua.
- **Thân hàm**: Đoạn mã thực hiện nhiệm vụ của hàm.

### Ví dụ
Dưới đây là một ví dụ đơn giản về việc định nghĩa và sử dụng hàm trong Go:

```go
package main

import "fmt"

// Hàm tính tổng hai số nguyên
func sum(a int, b int) int {
    return a + b
}

func main() {
    result := sum(3, 5)
    fmt.Println("Tổng là:", result) // Kết quả: Tổng là: 8
}
```

## Giải thích
Khi sử dụng hàm "func", có một số điều cần lưu ý:

1. **Tên hàm**: Tên hàm nên ngắn gọn nhưng có ý nghĩa, giúp người đọc dễ hiểu chức năng của hàm.
2. **Tham số và kiểu trả về**: Cần chú ý đến kiểu dữ liệu của tham số và kiểu trả về để tránh lỗi khi biên dịch.
3. **Phạm vi của biến**: Biến được định nghĩa trong thân hàm chỉ có phạm vi sử dụng trong hàm đó.
4. **Hàm không trả về giá trị**: Nếu bạn không cần hàm trả về giá trị, có thể không chỉ định kiểu trả về.

### Lỗi thường gặp
- Không chỉ định kiểu dữ liệu cho tham số hoặc giá trị trả về, sẽ dẫn đến lỗi biên dịch.
- Sử dụng tên hàm trùng lặp, gây ra xung đột tên.
- Quên gọi hàm trong hàm `main`, khiến mã không thực thi.

## Tóm tắt một câu
Hàm "func" trong Go cho phép lập trình viên định nghĩa các khối mã có thể tái sử dụng, giúp tổ chức và tối ưu hóa mã nguồn.