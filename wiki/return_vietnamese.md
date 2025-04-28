<!--
Meta Description: # Câu lệnh "return" trong Go: Cách sử dụng và lưu ý ## Tóm tắt Câu lệnh `return` trong ngôn ngữ lập trình Go được sử dụng để thoát khỏi một hàm và trả...
Meta Keywords: hàm, return, giá, trị, trả
-->

# Câu lệnh "return" trong Go: Cách sử dụng và lưu ý

## Tóm tắt
Câu lệnh `return` trong ngôn ngữ lập trình Go được sử dụng để thoát khỏi một hàm và trả về giá trị cho hàm gọi. Đây là một phần quan trọng trong việc quản lý luồng chương trình và trả về kết quả từ các phép toán hoặc xử lý dữ liệu.

## Tài liệu
Câu lệnh `return` trong Go có hai mục đích chính: thoát khỏi hàm và trả về giá trị. Mỗi hàm trong Go có thể trả về một hoặc nhiều giá trị, tùy thuộc vào định nghĩa của hàm. Cú pháp cơ bản của câu lệnh `return` như sau:

```go
return [giá trị]
```

### Mục đích
- **Thoát khỏi hàm**: Khi `return` được gọi, hàm sẽ dừng thực thi ngay lập tức, và điều khiển sẽ được chuyển lại cho hàm gọi.
- **Trả về giá trị**: Hàm có thể trả về một hoặc nhiều giá trị, và giá trị này sẽ được nhận bởi hàm gọi.

### Cách sử dụng
Khi định nghĩa một hàm, bạn có thể chỉ định các kiểu dữ liệu mà hàm sẽ trả về. Dưới đây là cú pháp cho một hàm trả về một giá trị:

```go
func tênHàm() kiểuDữLiệu {
    // logic hàm
    return giáTrị
}
```

Nếu hàm cần trả về nhiều giá trị, bạn có thể định nghĩa như sau:

```go
func tênHàm() (kiểu1, kiểu2) {
    // logic hàm
    return giáTrị1, giáTrị2
}
```

## Ví dụ
### Ví dụ 1: Hàm trả về một giá trị
```go
package main

import "fmt"

func cộng(a int, b int) int {
    return a + b
}

func main() {
    kếtQuả := cộng(3, 5)
    fmt.Println("Kết quả là:", kếtQuả)
}
```

### Ví dụ 2: Hàm trả về nhiều giá trị
```go
package main

import "fmt"

func chia(a, b int) (int, int) {
    return a / b, a % b
}

func main() {
    thương, dư := chia(10, 3)
    fmt.Println("Thương:", thương, "Dư:", dư)
}
```

## Giải thích
Mặc dù câu lệnh `return` rất đơn giản nhưng có một số lưu ý cần chú ý:
- **Không cần sử dụng `return`**: Nếu hàm không cần trả về giá trị nào, bạn có thể chỉ cần viết `return` mà không cần thêm giá trị nào.
- **Không cần giá trị khởi tạo**: Nếu bạn có một hàm trả về giá trị, các biến trả về không cần phải được khởi tạo trước khi sử dụng câu lệnh `return`. Chúng sẽ tự động được khởi tạo với giá trị mặc định của kiểu dữ liệu.
- **Vị trí câu lệnh `return`**: Một khi câu lệnh `return` được thực thi, mọi mã lệnh sau đó trong hàm sẽ không còn được thực thi.

## Tóm tắt một dòng
Câu lệnh `return` trong Go cho phép thoát khỏi hàm và trả về một hoặc nhiều giá trị cho hàm gọi, đóng vai trò quan trọng trong việc quản lý luồng chương trình.