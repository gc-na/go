<!--
Meta Description: # Biến trong Go: Cách sử dụng từ khóa "var" ## Tóm tắt Từ khóa "var" trong ngôn ngữ lập trình Go được sử dụng để khai báo biến. Đây là một phần quan t...
Meta Keywords: biến, var, khai, báo, trong
-->

# Biến trong Go: Cách sử dụng từ khóa "var"

## Tóm tắt
Từ khóa "var" trong ngôn ngữ lập trình Go được sử dụng để khai báo biến. Đây là một phần quan trọng trong việc quản lý dữ liệu và thực hiện các phép toán trong chương trình.

## Tài liệu
Từ khóa "var" cho phép bạn khai báo biến với các kiểu dữ liệu khác nhau. Cú pháp cơ bản để khai báo một biến là:

```go
var tênBiến kiểuDữLiệu
```

Bạn có thể khai báo nhiều biến cùng một lúc bằng cách sử dụng dấu phẩy:

```go
var biến1, biến2 kiểuDữLiệu
```

Ngoài ra, bạn có thể gán giá trị cho biến trong khi khai báo:

```go
var tênBiến kiểuDữLiệu = giáTrị
```

Nếu bạn không chỉ định kiểu dữ liệu, Go sẽ tự động suy diễn từ giá trị được gán:

```go
var tênBiến = giáTrị // Go tự động xác định kiểu dữ liệu
```

Khi sử dụng từ khóa "var", biến sẽ có phạm vi sống trong toàn bộ gói (package) mà nó được khai báo.

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng từ khóa "var":

1. Khai báo biến đơn giản:
   ```go
   var x int
   x = 10
   ```

2. Khai báo nhiều biến:
   ```go
   var a, b int
   a = 5
   b = 10
   ```

3. Khai báo và gán giá trị:
   ```go
   var name string = "John Doe"
   ```

4. Suy diễn kiểu dữ liệu:
   ```go
   var age = 30 // Go sẽ xác định age là int
   ```

5. Khai báo biến toàn cục:
   ```go
   var globalVar = "This is a global variable"
   ```

## Giải thích
Khi sử dụng từ khóa "var", có một số lưu ý và cạm bẫy mà lập trình viên cần chú ý:

- **Phạm vi sống của biến**: Biến khai báo bằng "var" có thể có phạm vi sống toàn cục hoặc cục bộ, tùy thuộc vào nơi nó được khai báo.
- **Không gán giá trị**: Nếu bạn khai báo biến mà không gán giá trị, Go sẽ khởi tạo biến đó với giá trị mặc định của kiểu dữ liệu tương ứng (ví dụ, int là 0, string là "" (chuỗi rỗng)).
- **Khai báo trùng tên**: Nếu khai báo biến với cùng tên trong cùng một phạm vi, bạn sẽ gặp lỗi biên dịch. Lập trình viên cần chắc chắn rằng tên biến là duy nhất trong phạm vi của nó.

## Tóm tắt một dòng
Từ khóa "var" trong Go được sử dụng để khai báo biến với khả năng chỉ định kiểu dữ liệu và gán giá trị, giúp quản lý dữ liệu trong chương trình hiệu quả.