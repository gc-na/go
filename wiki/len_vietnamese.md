<!--
Meta Description: # Hàm len trong Go: Cách sử dụng và ứng dụng ## Tóm tắt Hàm `len` trong ngôn ngữ lập trình Go được sử dụng để trả về độ dài của các kiểu dữ liệu khác ...
Meta Keywords: len, trong, dụng, hàm, slice
-->

# Hàm len trong Go: Cách sử dụng và ứng dụng

## Tóm tắt
Hàm `len` trong ngôn ngữ lập trình Go được sử dụng để trả về độ dài của các kiểu dữ liệu khác nhau như chuỗi, mảng, slice, và bản đồ.

## Tài liệu
Hàm `len` là một hàm tích hợp sẵn trong Go, cho phép lập trình viên xác định kích thước hoặc độ dài của một biến. Cú pháp của hàm này rất đơn giản:

```go
len(v)
```

Trong đó, `v` có thể là một chuỗi, mảng, slice, hoặc bản đồ. Hàm sẽ trả về một giá trị kiểu `int` biểu thị số lượng phần tử hoặc ký tự.

### Mục đích
Hàm `len` giúp lập trình viên dễ dàng kiểm tra số lượng phần tử trong một cấu trúc dữ liệu, từ đó có thể thực hiện các thao tác phù hợp trong quá trình xử lý dữ liệu.

### Cách sử dụng
- **Chuỗi**: Khi sử dụng với chuỗi, `len` sẽ trả về số ký tự trong chuỗi.
- **Mảng**: Đối với mảng, nó sẽ trả về số lượng phần tử trong mảng.
- **Slice**: Hàm sẽ trả lại số lượng phần tử hiện có trong slice.
- **Bản đồ**: Khi sử dụng với bản đồ, `len` sẽ trả về số lượng cặp khóa-giá trị trong bản đồ.

## Ví dụ
### Sử dụng với chuỗi
```go
package main

import "fmt"

func main() {
    str := "Hello, Go!"
    fmt.Println(len(str)) // Kết quả: 10
}
```

### Sử dụng với mảng
```go
package main

import "fmt"

func main() {
    arr := [5]int{1, 2, 3, 4, 5}
    fmt.Println(len(arr)) // Kết quả: 5
}
```

### Sử dụng với slice
```go
package main

import "fmt"

func main() {
    slice := []int{10, 20, 30}
    fmt.Println(len(slice)) // Kết quả: 3
}
```

### Sử dụng với bản đồ
```go
package main

import "fmt"

func main() {
    m := map[string]int{"a": 1, "b": 2}
    fmt.Println(len(m)) // Kết quả: 2
}
```

## Giải thích
Mặc dù `len` rất hữu ích, có một số điểm cần lưu ý:
- Hàm `len` không kiểm tra giá trị `nil`. Nếu bạn gọi `len` trên một slice hoặc bản đồ `nil`, nó sẽ trả về 0 mà không gây ra lỗi.
- Đối với các chuỗi có ký tự Unicode, `len` trả về số byte thay vì số ký tự. Để lấy số ký tự, bạn cần sử dụng `utf8.RuneCountInString(str)` từ gói `unicode/utf8`.

## Tóm tắt một dòng
Hàm `len` trong Go cho phép lập trình viên xác định độ dài của chuỗi, mảng, slice và bản đồ một cách nhanh chóng và dễ dàng.