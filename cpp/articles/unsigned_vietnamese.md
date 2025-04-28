<!--
Meta Description: # Sử Dụng "unsigned" Trong C++ ## Tóm tắt Trong C++, từ khóa "unsigned" được sử dụng để khai báo các kiểu dữ liệu số nguyên không dấu, cho phép lưu tr...
Meta Keywords: unsigned, giá, trị, không, các
-->

# Sử Dụng "unsigned" Trong C++

## Tóm tắt
Trong C++, từ khóa "unsigned" được sử dụng để khai báo các kiểu dữ liệu số nguyên không dấu, cho phép lưu trữ các giá trị dương lớn hơn so với các kiểu số nguyên có dấu.

## Tài liệu
### Mục đích
Từ khóa "unsigned" được sử dụng trong C++ để xác định rằng một biến số nguyên sẽ chỉ nhận giá trị không âm (0 và các số dương). Điều này mở rộng khoảng giá trị mà biến có thể lưu trữ, gấp đôi kích thước dương so với tương ứng với số nguyên có dấu.

### Cách sử dụng
Khi khai báo một biến, bạn có thể thêm từ khóa "unsigned" trước kiểu dữ liệu số nguyên. Ví dụ:

```cpp
unsigned int x; // Khai báo một biến số nguyên không dấu
```

Các kiểu dữ liệu có thể sử dụng với "unsigned" bao gồm:
- `unsigned int`
- `unsigned short`
- `unsigned long`
- `unsigned long long`

### Chi tiết
- `unsigned int`: Thường có kích thước 4 byte, cho phép lưu trữ giá trị từ 0 đến 4,294,967,295.
- `unsigned short`: Kích thước thường là 2 byte, cho phép lưu trữ giá trị từ 0 đến 65,535.
- `unsigned long`: Có kích thước 4 hoặc 8 byte tùy thuộc vào hệ thống, cho phép lưu trữ giá trị rất lớn.
- `unsigned long long`: Thường có kích thước 8 byte, cho phép lưu trữ giá trị từ 0 đến 18,446,744,073,709,551,615.

## Ví dụ
### Ví dụ cơ bản
```cpp
#include <iostream>
using namespace std;

int main() {
    unsigned int a = 10;
    unsigned int b = 20;
    unsigned int sum = a + b;

    cout << "Tổng của a và b là: " << sum << endl; // Kết quả: 30
    return 0;
}
```

### Ví dụ với kiểu dữ liệu khác
```cpp
#include <iostream>
using namespace std;

int main() {
    unsigned short num = 50000;
    cout << "Giá trị của num là: " << num << endl; // Kết quả: 50000

    unsigned long long bigNum = 12345678901234;
    cout << "Giá trị của bigNum là: " << bigNum << endl; // Kết quả: 12345678901234
    return 0;
}
```

## Giải thích
Khi sử dụng "unsigned", bạn cần lưu ý một số điểm sau:
- **Không thể lưu trữ giá trị âm**: Nếu bạn cố gắng gán một giá trị âm cho một biến không dấu, kết quả sẽ không như mong đợi (có thể dẫn đến giá trị không hợp lệ).
- **Quá dòng**: Nếu bạn thực hiện các phép toán và kết quả vượt quá giới hạn tối đa của kiểu dữ liệu, điều này sẽ dẫn đến hành vi không xác định.
- **Phép toán với số âm**: Khi sử dụng các phép toán với số âm và số không dấu, cần cẩn thận vì có thể dẫn đến những kết quả bất ngờ.

## Tóm tắt một dòng
Từ khóa "unsigned" trong C++ cho phép khai báo các kiểu dữ liệu số nguyên không dấu, mở rộng khoảng giá trị lưu trữ cho các biến số nguyên.