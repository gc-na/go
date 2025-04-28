<!--
Meta Description: # Hàm Append trong Go: Cách Sử Dụng và Ví Dụ ## Tóm tắt Hàm `append` trong ngôn ngữ lập trình Go được sử dụng để thêm các phần tử vào slice, một kiểu ...
Meta Keywords: slice, append, thêm, phần, một
-->

# Hàm Append trong Go: Cách Sử Dụng và Ví Dụ

## Tóm tắt
Hàm `append` trong ngôn ngữ lập trình Go được sử dụng để thêm các phần tử vào slice, một kiểu dữ liệu linh hoạt và mạnh mẽ giúp quản lý danh sách các giá trị.

## Tài liệu
Hàm `append` là một phần quan trọng của ngôn ngữ Go, cho phép bạn mở rộng một slice bằng cách thêm các phần tử mới vào cuối slice hiện tại. Cú pháp của hàm `append` như sau:

```go
func append(s []Type, elems ...Type) []Type
```

- **s**: Slice mà bạn muốn thêm phần tử vào.
- **elems**: Một hoặc nhiều phần tử bạn muốn thêm vào slice.

Mục đích chính của `append` là tạo ra một slice mới với các phần tử đã được thêm vào. Nếu slice ban đầu không đủ dung lượng để chứa các phần tử mới, Go sẽ tự động cấp phát bộ nhớ mới và sao chép dữ liệu.

### Sử dụng
Để sử dụng hàm `append`, bạn chỉ cần gọi nó với slice và các phần tử bạn muốn thêm. Ví dụ:

```go
slice := []int{1, 2, 3}
slice = append(slice, 4, 5)
```

Kết quả của đoạn mã trên là slice mới chứa các giá trị `[1, 2, 3, 4, 5]`.

## Ví dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng hàm `append`:

### Ví dụ 1: Thêm một phần tử vào slice
```go
package main

import "fmt"

func main() {
    numbers := []int{1, 2, 3}
    numbers = append(numbers, 4)
    fmt.Println(numbers) // Kết quả: [1 2 3 4]
}
```

### Ví dụ 2: Thêm nhiều phần tử vào slice
```go
package main

import "fmt"

func main() {
    fruits := []string{"táo", "chuối"}
    fruits = append(fruits, "cam", "quýt")
    fmt.Println(fruits) // Kết quả: [táo chuối cam quýt]
}
```

### Ví dụ 3: Thêm một slice vào slice khác
```go
package main

import "fmt"

func main() {
    slice1 := []int{1, 2, 3}
    slice2 := []int{4, 5, 6}
    slice1 = append(slice1, slice2...) // Sử dụng "..." để thêm toàn bộ phần tử từ slice2
    fmt.Println(slice1) // Kết quả: [1 2 3 4 5 6]
}
```

## Giải thích
Mặc dù `append` rất hữu ích, có một số điều cần lưu ý:

1. **Cấp phát bộ nhớ**: Khi sử dụng `append`, nếu slice ban đầu đã đạt đến giới hạn của nó, Go sẽ cấp phát bộ nhớ mới cho slice. Điều này có thể dẫn đến việc các biến khác tham chiếu đến slice ban đầu không được cập nhật, vì vậy bạn cần gán lại slice sau khi gọi `append`.

2. **Thêm slice khác**: Khi thêm một slice khác vào slice hiện tại, hãy nhớ sử dụng dấu chấm và phẩy (`...`) để chỉ ra rằng bạn muốn thêm các phần tử của slice đó, chứ không phải là chính slice.

3. **Kiểu dữ liệu**: Các phần tử mà bạn thêm vào slice phải có cùng kiểu dữ liệu với slice đó.

## Tóm tắt một dòng
Hàm `append` trong Go cho phép bạn mở rộng một slice bằng cách thêm một hoặc nhiều phần tử mới vào cuối slice.