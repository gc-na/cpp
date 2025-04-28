<!--
Meta Description: # C++: Câu lệnh "else" - Hướng dẫn chi tiết ## Tóm tắt Câu lệnh "else" trong C++ được sử dụng để chỉ định một khối mã sẽ được thực thi khi điều kiện t...
Meta Keywords: else, câu, lệnh, điều, kiện
-->

# C++: Câu lệnh "else" - Hướng dẫn chi tiết

## Tóm tắt
Câu lệnh "else" trong C++ được sử dụng để chỉ định một khối mã sẽ được thực thi khi điều kiện trong câu lệnh "if" không được thỏa mãn. Đây là một phần quan trọng trong cấu trúc điều kiện, giúp lập trình viên kiểm soát luồng chương trình một cách linh hoạt.

## Tài liệu
### Mục đích
Câu lệnh "else" cho phép lập trình viên xử lý các tình huống khác nhau trong chương trình bằng cách thực hiện các hành động khác nhau dựa trên điều kiện. Khi điều kiện trong câu lệnh "if" là sai, khối mã trong câu lệnh "else" sẽ được thực thi.

### Cách sử dụng
Câu lệnh "else" thường được sử dụng trong kết hợp với câu lệnh "if". Cú pháp cơ bản của câu lệnh "if" và "else" như sau:

```cpp
if (điều_kiện) {
    // Khối mã thực thi nếu điều kiện đúng
} else {
    // Khối mã thực thi nếu điều kiện sai
}
```

Bạn cũng có thể sử dụng câu lệnh "else if" để kiểm tra nhiều điều kiện khác nhau:

```cpp
if (điều_kiện_1) {
    // Khối mã thực thi nếu điều kiện 1 đúng
} else if (điều_kiện_2) {
    // Khối mã thực thi nếu điều kiện 2 đúng
} else {
    // Khối mã thực thi nếu tất cả các điều kiện trên đều sai
}
```

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng câu lệnh "else":

```cpp
#include <iostream>
using namespace std;

int main() {
    int a;
    cout << "Nhập một số nguyên: ";
    cin >> a;

    if (a > 0) {
        cout << "Số dương." << endl;
    } else {
        cout << "Số không dương." << endl;
    }

    return 0;
}
```

Trong ví dụ này, nếu người dùng nhập một số dương, chương trình sẽ in ra "Số dương.". Ngược lại, nếu số đó không dương (bao gồm cả số 0 và số âm), chương trình sẽ in ra "Số không dương.".

## Giải thích
### Những cạm bẫy phổ biến
- **Quên dấu ngoặc nhọn**: Khi không sử dụng dấu ngoặc nhọn cho khối mã trong câu lệnh "if" hoặc "else", chỉ có câu lệnh đầu tiên ngay sau sẽ được coi là một phần của khối đó. Điều này có thể dẫn đến lỗi logic.
- **Thiếu điều kiện**: Đảm bảo rằng điều kiện trong câu lệnh "if" được kiểm tra chính xác. Việc không kiểm tra đúng điều kiện có thể làm cho khối mã trong "else" không được thực thi như mong muốn.
- **Sự nhầm lẫn giữa "if" và "else"**: Đôi khi lập trình viên có thể nhầm lẫn cấu trúc "if-else" với các cấu trúc điều kiện khác. Cần phải nắm rõ cách hoạt động của chúng để tránh lỗi.

## Tóm tắt một dòng
Câu lệnh "else" trong C++ cho phép lập trình viên thực thi một khối mã nhất định khi điều kiện trong câu lệnh "if" không được thỏa mãn.