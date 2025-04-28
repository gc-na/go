<!--
Meta Description: # Lệnh "copy" trong Go: Sao chép dữ liệu một cách hiệu quả ## Tóm tắt Lệnh "copy" trong Go được sử dụng để sao chép dữ liệu từ một slice sang một slic...
Meta Keywords: slice, copy, sao, chép, liệu
-->

# Lệnh "copy" trong Go: Sao chép dữ liệu một cách hiệu quả

## Tóm tắt
Lệnh "copy" trong Go được sử dụng để sao chép dữ liệu từ một slice sang một slice khác. Đây là một tính năng quan trọng giúp quản lý bộ nhớ và xử lý dữ liệu trong các ứng dụng Go.

## Tài liệu
Lệnh `copy` trong Go có cú pháp như sau:

```go
n := copy(dst, src)
```

- **dst**: Slice đích mà dữ liệu sẽ được sao chép đến.
- **src**: Slice nguồn mà dữ liệu sẽ được sao chép từ đó.
- **n**: Số lượng phần tử đã được sao chép, giá trị trả về của hàm `copy`.

### Mục đích
Lệnh `copy` được sử dụng để sao chép các phần tử từ slice nguồn sang slice đích một cách an toàn và hiệu quả. Hàm này giúp bạn dễ dàng quản lý dữ liệu mà không cần lo lắng về việc ghi đè lên dữ liệu cũ trong slice đích.

### Cách sử dụng
Để sử dụng lệnh `copy`, bạn cần đảm bảo rằng slice đích (`dst`) có đủ dung lượng để chứa dữ liệu từ slice nguồn (`src`). Nếu không, chỉ các phần tử trong phạm vi của slice đích sẽ được sao chép.

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng lệnh `copy`:

### Ví dụ 1: Sao chép slice cơ bản
```go
package main

import "fmt"

func main() {
    src := []int{1, 2, 3, 4, 5}
    dst := make([]int, 3)

    n := copy(dst, src)
    fmt.Println(dst) // Kết quả: [1 2 3]
    fmt.Println(n)   // Kết quả: 3
}
```

### Ví dụ 2: Sao chép toàn bộ slice
```go
package main

import "fmt"

func main() {
    src := []string{"a", "b", "c"}
    dst := make([]string, len(src))

    n := copy(dst, src)
    fmt.Println(dst) // Kết quả: [a b c]
    fmt.Println(n)   // Kết quả: 3
}
```

## Giải thích
Khi sử dụng lệnh `copy`, có một số điều cần lưu ý:

- **Dung lượng slice**: Nếu slice đích nhỏ hơn slice nguồn, chỉ các phần tử tương ứng trong slice đích sẽ được sao chép, và giá trị trả về sẽ là số lượng phần tử đã sao chép.
- **Bảo toàn dữ liệu**: `copy` sẽ không thay đổi các phần tử trong slice nguồn. Nên bạn có thể yên tâm rằng dữ liệu gốc vẫn được giữ nguyên.
- **Hiệu suất**: `copy` được tối ưu hóa để làm việc nhanh chóng, và thường là lựa chọn tốt hơn so với việc sao chép từng phần tử bằng vòng lặp.

## Tóm tắt một dòng
Lệnh `copy` trong Go cho phép sao chép dữ liệu từ một slice sang một slice khác một cách an toàn và hiệu quả.