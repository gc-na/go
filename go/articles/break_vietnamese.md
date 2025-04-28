<!--
Meta Description: # Lệnh "break" trong Go: Cách sử dụng và ví dụ ## Tóm tắt Lệnh `break` trong ngôn ngữ lập trình Go được sử dụng để thoát khỏi vòng lặp hoặc câu lệnh s...
Meta Keywords: lệnh, break, vòng, lặp, trong
-->

# Lệnh "break" trong Go: Cách sử dụng và ví dụ

## Tóm tắt
Lệnh `break` trong ngôn ngữ lập trình Go được sử dụng để thoát khỏi vòng lặp hoặc câu lệnh switch, giúp điều khiển luồng thực thi của chương trình một cách hiệu quả.

## Tài liệu
### Mục đích
Lệnh `break` cho phép lập trình viên kết thúc sớm một vòng lặp (for, range) hoặc một câu lệnh switch khi một điều kiện nhất định được thỏa mãn.

### Cách sử dụng
Cú pháp cơ bản của lệnh `break` như sau:
```go
break
```
Lệnh `break` có thể được sử dụng trong bất kỳ vòng lặp nào, bao gồm:
- Vòng lặp `for`
- Vòng lặp `range`
- Câu lệnh `switch`

### Chi tiết
Khi lệnh `break` được thực thi, chương trình sẽ ngay lập tức thoát khỏi vòng lặp hoặc câu lệnh switch đang chạy, và tiếp tục thực hiện các câu lệnh phía sau nó. Lệnh này không cần phải có điều kiện đi kèm, nhưng thông thường sẽ được sử dụng trong các cấu trúc điều kiện để kiểm soát khi nào thì thoát khỏi vòng lặp.

## Ví dụ
### Ví dụ 1: Sử dụng lệnh break trong vòng lặp for
```go
package main

import "fmt"

func main() {
    for i := 0; i < 10; i++ {
        if i == 5 {
            break
        }
        fmt.Println(i)
    }
}
```
**Kết quả:**
```
0
1
2
3
4
```

### Ví dụ 2: Sử dụng lệnh break trong câu lệnh switch
```go
package main

import "fmt"

func main() {
    day := 3
    switch day {
    case 1:
        fmt.Println("Thứ Hai")
    case 2:
        fmt.Println("Thứ Ba")
    case 3:
        fmt.Println("Thứ Tư")
        break // Thoát khỏi switch
    case 4:
        fmt.Println("Thứ Năm")
    }
}
```
**Kết quả:**
```
Thứ Tư
```

## Giải thích
- **Điểm cần chú ý:** Khi sử dụng `break`, hãy chắc chắn rằng bạn đang ở trong vòng lặp hoặc câu lệnh switch mà bạn muốn thoát ra. Sử dụng `break` bên ngoài của các cấu trúc này sẽ gây ra lỗi biên dịch.
- **Các vấn đề thường gặp:** Một số lập trình viên mới có thể nhầm lẫn giữa `break` và `continue`. `break` sẽ thoát khỏi vòng lặp hoàn toàn, trong khi `continue` chỉ bỏ qua phần còn lại của vòng lặp hiện tại và tiếp tục với vòng lặp tiếp theo.

## Tóm tắt một dòng
Lệnh `break` trong Go cho phép lập trình viên kết thúc sớm một vòng lặp hoặc câu lệnh switch, giúp điều khiển luồng thực thi một cách linh hoạt.