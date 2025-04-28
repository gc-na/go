<!--
Meta Description: # Câu lệnh "case" trong Go: Hướng dẫn Chi tiết và Ví dụ ## Tóm tắt Câu lệnh "case" trong Go được sử dụng để thực hiện các lựa chọn điều kiện trong cấu...
Meta Keywords: case, trong, lệnh, một, câu
-->

# Câu lệnh "case" trong Go: Hướng dẫn Chi tiết và Ví dụ

## Tóm tắt
Câu lệnh "case" trong Go được sử dụng để thực hiện các lựa chọn điều kiện trong cấu trúc switch, cho phép lập trình viên kiểm soát luồng thực thi của chương trình dựa vào giá trị của một biểu thức.

## Tài liệu
Câu lệnh "case" trong Go là một phần của cấu trúc `switch`, cho phép bạn kiểm tra một biểu thức và so sánh nó với nhiều giá trị khác nhau. Cấu trúc này giúp làm cho mã nguồn trở nên dễ đọc và tối ưu hơn so với việc sử dụng nhiều câu lệnh `if-else`.

### Cách sử dụng
Cú pháp cơ bản của câu lệnh `switch` với `case` như sau:

```go
switch biểu_thức {
case giá_trị_1:
    // Thực hiện khi biểu thức bằng giá_trị_1
case giá_trị_2:
    // Thực hiện khi biểu thức bằng giá_trị_2
default:
    // Thực hiện nếu không có giá trị nào khớp
}
```

Trong đó, `biểu_thức` là giá trị sẽ được kiểm tra, và các `giá_trị` là các giá trị mà bạn muốn so sánh với `biểu_thức`. Nếu không có `case` nào khớp, khối lệnh trong `default` sẽ được thực thi (nếu có).

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng câu lệnh `case` trong Go:

```go
package main

import (
    "fmt"
)

func main() {
    day := "Thứ Hai"

    switch day {
    case "Thứ Hai":
        fmt.Println("Hôm nay là thứ Hai")
    case "Thứ Ba":
        fmt.Println("Hôm nay là thứ Ba")
    case "Thứ Tư":
        fmt.Println("Hôm nay là thứ Tư")
    default:
        fmt.Println("Ngày không xác định")
    }
}
```

Kết quả của chương trình trên sẽ là:
```
Hôm nay là thứ Hai
```

## Giải thích
Mặc dù câu lệnh `case` trong Go rất hữu ích, nhưng có một số điểm cần lưu ý:

1. **Không có break**: Trong Go, không cần phải sử dụng câu lệnh `break` để dừng thực thi trong mỗi case, bởi vì Go tự động kết thúc sau khi một case được thực thi.
  
2. **Nhiều giá trị**: Bạn có thể kiểm tra nhiều giá trị trong một case bằng cách sử dụng dấu phẩy, ví dụ:
   ```go
   switch x {
   case 1, 2:
       fmt.Println("x là 1 hoặc 2")
   }
   ```

3. **Kiểm tra kiểu**: Bạn cũng có thể sử dụng `switch` để kiểm tra kiểu dữ liệu:
   ```go
   var i interface{} = "Hello"
   switch i.(type) {
   case string:
       fmt.Println("i là một chuỗi")
   case int:
       fmt.Println("i là một số nguyên")
   default:
       fmt.Println("i là kiểu khác")
   }
   ```

## Tóm tắt một dòng
Câu lệnh "case" trong Go cho phép lập trình viên kiểm soát luồng chương trình thông qua cấu trúc `switch`, giúp mã nguồn trở nên rõ ràng và hiệu quả hơn.