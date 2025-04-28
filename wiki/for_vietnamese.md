<!--
Meta Description: # Câu Lệnh "for" Trong Ngôn Ngữ Lập Trình Go: Cách Sử Dụng và Ví Dụ ## Tóm Tắt Câu lệnh "for" trong Go là cấu trúc lặp duy nhất, cho phép lập trình vi...
Meta Keywords: lặp, lệnh, fmt, câu, qua
-->

# Câu Lệnh "for" Trong Ngôn Ngữ Lập Trình Go: Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Câu lệnh "for" trong Go là cấu trúc lặp duy nhất, cho phép lập trình viên lặp qua các dãy số, mảng, slice, bản đồ và các cấu trúc dữ liệu khác. Câu lệnh này hỗ trợ nhiều hình thức khác nhau, từ lặp vô hạn đến lặp có điều kiện.

## Tài Liệu
Câu lệnh "for" trong Go được sử dụng để thực hiện các vòng lặp, giúp lập trình viên thực hiện các thao tác lặp đi lặp lại. Cú pháp cơ bản của câu lệnh "for" như sau:

```go
for [khởi tạo]; [điều kiện]; [cập nhật] {
    // mã lệnh cần thực hiện
}
```

### Các Hình Thức Của Câu Lệnh "for":
1. **Lặp qua một dãy số:**
   ```go
   for i := 0; i < 10; i++ {
       fmt.Println(i)
   }
   ```

2. **Lặp vô hạn:**
   ```go
   for {
       // mã lệnh ở đây sẽ chạy mãi mãi
   }
   ```

3. **Lặp qua slice hoặc mảng:**
   ```go
   numbers := []int{1, 2, 3, 4, 5}
   for i, num := range numbers {
       fmt.Println(i, num)
   }
   ```

4. **Lặp qua bản đồ:**
   ```go
   myMap := map[string]int{"a": 1, "b": 2}
   for key, value := range myMap {
       fmt.Println(key, value)
   }
   ```

## Ví Dụ
### Ví Dụ 1: Lặp qua số
```go
package main

import "fmt"

func main() {
    for i := 0; i < 5; i++ {
        fmt.Println("Số hiện tại:", i)
    }
}
```

### Ví Dụ 2: Lặp vô hạn
```go
package main

import "fmt"

func main() {
    i := 0
    for {
        fmt.Println("Lặp vô hạn:", i)
        i++
        if i >= 5 {
            break
        }
    }
}
```

### Ví Dụ 3: Sử dụng `range`
```go
package main

import "fmt"

func main() {
    fruits := []string{"apple", "banana", "cherry"}
    for index, fruit := range fruits {
        fmt.Println(index, fruit)
    }
}
```

## Giải Thích
Khi sử dụng câu lệnh "for", một số lưu ý cần nhớ:
- **Lặp vô hạn:** Nếu không có điều kiện dừng, vòng lặp sẽ chạy mãi mãi. Hãy luôn đảm bảo có điều kiện thoát.
- **Sử dụng `break` và `continue`:** Bạn có thể sử dụng `break` để dừng vòng lặp hoặc `continue` để bỏ qua một lần lặp.
- **Lưu ý về chỉ số:** Khi lặp qua slice hoặc mảng, chỉ số bắt đầu từ 0. Đảm bảo rằng bạn không truy cập ra ngoài chỉ số của mảng.

## Tóm Tắt Một Dòng
Câu lệnh "for" trong Go là cấu trúc lặp mạnh mẽ và linh hoạt, cho phép lập trình viên thực hiện các thao tác lặp một cách dễ dàng và hiệu quả.