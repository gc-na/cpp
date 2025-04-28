<!--
Meta Description: # C++ "do" - Cấu trúc lặp do-while trong C++ ## Tóm tắt Cấu trúc lặp `do-while` trong C++ cho phép thực thi một đoạn mã ít nhất một lần và tiếp tục lặ...
Meta Keywords: lặp, while, một, vòng, điều
-->

# C++ "do" - Cấu trúc lặp do-while trong C++

## Tóm tắt
Cấu trúc lặp `do-while` trong C++ cho phép thực thi một đoạn mã ít nhất một lần và tiếp tục lặp lại cho đến khi điều kiện xác định là sai.

## Tài liệu
### Mục đích
Cấu trúc `do-while` được sử dụng để thực hiện các tác vụ lặp đi lặp lại trong khi một điều kiện cụ thể còn đúng. Khác với vòng lặp `while`, vòng lặp `do-while` đảm bảo rằng đoạn mã trong thân vòng lặp sẽ luôn được thực hiện ít nhất một lần.

### Cú pháp
```cpp
do {
    // Các câu lệnh
} while (điều_kiện);
```

### Chi tiết
- **do**: Từ khóa bắt đầu của vòng lặp.
- **{ ... }**: Thân vòng lặp, nơi chứa các câu lệnh sẽ được thực thi.
- **while**: Từ khóa theo sau thân vòng lặp.
- **(điều_kiện)**: Một biểu thức điều kiện boolean. Nếu điều kiện này đúng, vòng lặp sẽ tiếp tục; nếu sai, vòng lặp sẽ dừng lại.

## Ví dụ
### Ví dụ cơ bản 1: Sử dụng `do-while` để in ra các số từ 1 đến 5
```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    do {
        cout << i << endl;
        i++;
    } while (i <= 5);
    return 0;
}
```

### Ví dụ cơ bản 2: Nhập số từ người dùng cho đến khi họ nhập số 0
```cpp
#include <iostream>
using namespace std;

int main() {
    int number;
    do {
        cout << "Nhập một số (0 để dừng): ";
        cin >> number;
    } while (number != 0);
    return 0;
}
```

## Giải thích
- **Điều kiện chỉ kiểm tra sau khi thực thi**: Vòng lặp `do-while` sẽ luôn thực hiện ít nhất một lần, ngay cả khi điều kiện ban đầu là sai.
- **Lưu ý về dấu chấm phẩy**: Cần phải chú ý đến dấu chấm phẩy sau điều kiện `while`. Nếu bỏ quên, có thể dẫn đến lỗi hoặc hành vi không mong muốn.

## Tóm tắt một dòng
Cấu trúc lặp `do-while` trong C++ cho phép thực hiện một đoạn mã ít nhất một lần và tiếp tục lặp cho đến khi điều kiện không còn đúng.