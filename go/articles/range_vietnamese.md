<!--
Meta Description: # Sử Dụng Câu Lệnh "range" Trong Ngôn Ngữ Go: Hướng Dẫn Chi Tiết ## Tóm Tắt Câu lệnh `range` trong Go là một công cụ mạnh mẽ cho phép lặp qua các cấu ...
Meta Keywords: value, qua, lặp, range, key
-->

# Sử Dụng Câu Lệnh "range" Trong Ngôn Ngữ Go: Hướng Dẫn Chi Tiết

## Tóm Tắt
Câu lệnh `range` trong Go là một công cụ mạnh mẽ cho phép lặp qua các cấu trúc dữ liệu như mảng, slice, string, map và channel, giúp đơn giản hóa việc truy cập và xử lý dữ liệu.

## Tài Liệu
### Mục Đích
Câu lệnh `range` cung cấp một cách hiệu quả để lặp qua các phần tử trong các kiểu dữ liệu khác nhau mà không cần phải quản lý chỉ số thủ công, giúp mã nguồn trở nên sạch sẽ và dễ đọc hơn.

### Cách Sử Dụng
Cú pháp cơ bản của câu lệnh `range` như sau:

```go
for key, value := range collection {
    // xử lý key và value
}
```

Trong đó:
- `collection` có thể là một mảng, slice, string, map hoặc channel.
- `key` và `value` là các biến sẽ nhận giá trị của phần tử trong mỗi vòng lặp. 

### Chi Tiết
- **Mảng và Slice**: Khi lặp qua mảng hoặc slice, `key` sẽ là chỉ số của phần tử, còn `value` là giá trị của phần tử đó.
- **String**: Khi lặp qua string, `key` sẽ là chỉ số của ký tự, còn `value` là ký tự đó dưới dạng giá trị rune.
- **Map**: Khi lặp qua map, `key` là khóa, và `value` là giá trị tương ứng với khóa đó.
- **Channel**: Khi lặp qua channel, `value` sẽ là giá trị được gửi qua channel.

## Ví Dụ
### Lặp Qua Mảng
```go
arr := []int{1, 2, 3, 4}
for index, value := range arr {
    fmt.Printf("Index: %d, Value: %d\n", index, value)
}
```

### Lặp Qua String
```go
str := "Hello"
for index, char := range str {
    fmt.Printf("Index: %d, Char: %c\n", index, char)
}
```

### Lặp Qua Map
```go
m := map[string]int{"A": 1, "B": 2}
for key, value := range m {
    fmt.Printf("Key: %s, Value: %d\n", key, value)
}
```

### Lặp Qua Channel
```go
ch := make(chan int)
go func() {
    for i := 0; i < 5; i++ {
        ch <- i
    }
    close(ch)
}()
for value := range ch {
    fmt.Println(value)
}
```

## Giải Thích
- **Chuyển Giá Trị**: Khi sử dụng `range`, các giá trị được sao chép. Nếu bạn cần tham chiếu đến giá trị gốc (như trong trường hợp của slice), bạn cần sử dụng `&` để lấy địa chỉ.
- **Bỏ Qua Giá Trị**: Nếu bạn không cần một trong hai giá trị (key hoặc value), bạn có thể bỏ qua chúng bằng cách sử dụng dấu gạch dưới `_`. Ví dụ: `for _, value := range arr {}`.
- **Khi Sử Dụng Map**: Không có thứ tự xác định khi lặp qua các phần tử của map, do đó thứ tự có thể thay đổi mỗi lần bạn lặp.

## Tóm Tắt Một Dòng
Câu lệnh `range` trong Go là một công cụ hiệu quả để lặp qua các kiểu dữ liệu như mảng, slice, string, map và channel, giúp đơn giản hóa việc truy cập và xử lý dữ liệu.