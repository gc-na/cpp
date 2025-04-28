<!--
Meta Description: # Kiểu Dữ Liệu int trong C++ ## Tóm tắt Kiểu dữ liệu `int` trong C++ là kiểu số nguyên cơ bản được sử dụng để lưu trữ các giá trị số nguyên trong chươ...
Meta Keywords: int, kiểu, dụng, các, trong
-->

# Kiểu Dữ Liệu int trong C++

## Tóm tắt
Kiểu dữ liệu `int` trong C++ là kiểu số nguyên cơ bản được sử dụng để lưu trữ các giá trị số nguyên trong chương trình. Nó là một phần quan trọng trong lập trình C++, cho phép lập trình viên thực hiện các phép toán và xử lý dữ liệu hiệu quả.

## Tài liệu
### Mục đích
Kiểu `int` (integer) được sử dụng để đại diện cho các số nguyên, có thể là số dương, số âm hoặc số không. Kiểu này thường được sử dụng trong các phép toán số học, vòng lặp, và các cấu trúc điều kiện.

### Sử dụng
Để khai báo một biến kiểu `int`, bạn chỉ cần sử dụng từ khóa `int` theo sau là tên biến. Ví dụ:

```cpp
int a;
int b = 10;
```

Biến `a` được khai báo nhưng chưa được gán giá trị, trong khi biến `b` được gán giá trị 10.

### Chi tiết
- Kích thước: Kích thước của kiểu `int` thường là 4 byte (32 bit) trên hầu hết các hệ thống hiện đại, nhưng điều này có thể thay đổi tùy thuộc vào kiến trúc của máy tính.
- Phạm vi giá trị: Phạm vi của biến kiểu `int` thường từ -2,147,483,648 đến 2,147,483,647. Để đại diện cho các số nguyên lớn hơn, bạn có thể sử dụng các kiểu khác như `long` hoặc `long long`.

## Ví dụ
### Ví dụ 1: Khai báo và gán giá trị
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 5;
    int y = 10;
    int sum = x + y;
    cout << "Tổng của x và y là: " << sum << endl;
    return 0;
}
```

### Ví dụ 2: Sử dụng trong vòng lặp
```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 5; i++) {
        cout << "Giá trị của i là: " << i << endl;
    }
    return 0;
}
```

## Giải thích
- **Lỗi phổ biến**: Một số lập trình viên mới có thể quên khởi tạo biến kiểu `int`, dẫn đến việc sử dụng giá trị ngẫu nhiên. Hãy luôn khởi tạo biến trước khi sử dụng.
- **Giới hạn**: Khi làm việc với các số lớn hơn phạm vi của `int`, bạn nên sử dụng `long` hoặc `long long` để tránh tràn số.
- **Tính toàn vẹn dữ liệu**: Sử dụng kiểu `int` cho các phép toán mà không có phần thập phân, vì số thực (float hoặc double) sẽ không phù hợp trong trường hợp này.

## Tóm tắt một câu
Kiểu dữ liệu `int` trong C++ là kiểu số nguyên cơ bản, cho phép lập trình viên thực hiện các phép toán số học và xử lý dữ liệu hiệu quả.