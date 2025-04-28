<!--
Meta Description: # Kiểu Dữ Liệu "short" trong C++ ## Tóm tắt Trong C++, kiểu dữ liệu `short` là một kiểu số nguyên dùng để lưu trữ các giá trị số nguyên với kích thước...
Meta Keywords: short, kiểu, dụng, các, trong
-->

# Kiểu Dữ Liệu "short" trong C++

## Tóm tắt
Trong C++, kiểu dữ liệu `short` là một kiểu số nguyên dùng để lưu trữ các giá trị số nguyên với kích thước nhỏ hơn so với kiểu `int`. Kiểu này thường được sử dụng khi cần tiết kiệm bộ nhớ mà không cần đến giá trị lớn.

## Tài liệu
### Mục đích
Kiểu `short` được sử dụng để lưu trữ các số nguyên có kích thước nhỏ hơn, với kích thước thường là 16 bit. Điều này giúp tiết kiệm không gian bộ nhớ, đặc biệt trong các ứng dụng yêu cầu nhiều biến số nguyên.

### Cú pháp
Cú pháp khai báo một biến kiểu `short` như sau:
```cpp
short variable_name;
```

### Sử dụng
Biến kiểu `short` có thể được khởi tạo và sử dụng tương tự như các kiểu số nguyên khác:
```cpp
short a = 10;
short b = -5;
short sum = a + b; // sum = 5
```

#### Phạm vi giá trị
- Kiểu `short` có thể lưu trữ giá trị từ -32,768 đến 32,767 (cho `short` có dấu).
- Nếu sử dụng `unsigned short`, phạm vi giá trị sẽ từ 0 đến 65,535.

## Ví dụ
### Ví dụ cơ bản
```cpp
#include <iostream>
using namespace std;

int main() {
    short a = 1000;         // Khai báo kiểu short
    short b = 2000;         // Khai báo kiểu short
    short sum = a + b;     // Tính tổng

    cout << "Tổng: " << sum << endl; // In ra tổng
    return 0;
}
```

### Ví dụ sử dụng `unsigned short`
```cpp
#include <iostream>
using namespace std;

int main() {
    unsigned short a = 60000; // Khai báo kiểu unsigned short
    unsigned short b = 1000;  // Khai báo kiểu unsigned short
    unsigned short sum = a + b; // Tính tổng

    cout << "Tổng: " << sum << endl; // Có thể xảy ra tràn số
    return 0;
}
```

## Giải thích
### Cạm bẫy phổ biến
- **Tràn số**: Khi giá trị của biến kiểu `short` vượt quá phạm vi cho phép, có thể xảy ra tình trạng tràn số, dẫn đến kết quả không mong muốn.
- **Khác biệt giữa `short` và `int`**: Mặc dù `short` có kích thước nhỏ hơn, nhưng trong một số trường hợp, trình biên dịch sẽ tự động chuyển đổi các phép toán sang kiểu `int`, có thể làm cho việc so sánh và tính toán trở nên không chính xác nếu không được xử lý cẩn thận.

### Lưu ý thêm
- Sử dụng `short` có thể không cần thiết trong mọi trường hợp, vì hầu hết các hệ thống hiện nay có đủ bộ nhớ để xử lý kiểu `int`. Tuy nhiên, trong các ứng dụng nhúng hoặc nơi mà bộ nhớ hạn chế, `short` có thể là lựa chọn tối ưu.

## Tóm tắt một dòng
Kiểu dữ liệu `short` trong C++ là một kiểu số nguyên có kích thước 16 bit, được sử dụng để lưu trữ các giá trị số nguyên nhỏ, giúp tiết kiệm bộ nhớ.