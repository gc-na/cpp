<!--
Meta Description: # Toán Tử "AND" trong C++ ## Tóm tắt Toán tử "AND" trong C++ là một toán tử logic dùng để thực hiện phép so sánh giữa hai biểu thức, trả về giá trị đú...
Meta Keywords: điều, toán, kiện, trong, dụng
-->

# Toán Tử "AND" trong C++

## Tóm tắt
Toán tử "AND" trong C++ là một toán tử logic dùng để thực hiện phép so sánh giữa hai biểu thức, trả về giá trị đúng (true) nếu cả hai biểu thức đều đúng, ngược lại trả về sai (false).

## Tài liệu
Toán tử "AND" trong C++ được biểu diễn bằng ký hiệu `&&`. Nó là một phần quan trọng trong lập trình điều kiện, cho phép lập trình viên kết hợp nhiều điều kiện lại với nhau. Cách sử dụng toán tử "AND" rất đơn giản, chỉ cần đặt nó giữa hai biểu thức điều kiện.

### Cú pháp:
```cpp
biểu_thức_1 && biểu_thức_2
```

### Mô tả:
- **Mục đích**: Toán tử "AND" được sử dụng để kiểm tra tính đúng đắn của nhiều điều kiện cùng một lúc. Nếu tất cả các điều kiện đều đúng, kết quả sẽ là true. Nếu ít nhất một điều kiện sai, kết quả sẽ là false.
- **Sử dụng**: Thường dùng trong các câu lệnh điều kiện như `if`, `while`, và `for`, để xác định xem một khối mã có nên được thực thi hay không.

## Ví dụ
### Ví dụ 1: Sử dụng trong câu lệnh if
```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10;
    int b = 20;

    if (a > 5 && b < 30) {
        cout << "Cả hai điều kiện đều đúng!" << endl;
    }
    return 0;
}
```

### Ví dụ 2: Sử dụng trong vòng lặp while
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 0;

    while (x < 5 && x >= 0) {
        cout << "Giá trị của x là: " << x << endl;
        x++;
    }
    return 0;
}
```

## Giải thích
Khi sử dụng toán tử "AND", có một số điều cần lưu ý:
- **Ngắn mạch (Short-circuit evaluation)**: C++ thực hiện kiểm tra điều kiện từ trái sang phải. Nếu điều kiện đầu tiên sai, điều kiện thứ hai sẽ không được kiểm tra vì kết quả đã xác định là false.
- **Kiểu dữ liệu**: Toán tử "AND" có thể được sử dụng với bất kỳ loại dữ liệu nào có thể được chuyển đổi thành kiểu bool (như số nguyên, số thực, v.v.). Tuy nhiên, hãy cẩn thận với các kiểu dữ liệu khác nhau để đảm bảo bạn có kết quả như mong muốn.
- **Sự nhầm lẫn với toán tử bitwise**: Đừng nhầm lẫn toán tử "AND" logic `&&` với toán tử "AND" bitwise `&`. Chúng có cách hoạt động khác nhau và thường được sử dụng trong các ngữ cảnh khác nhau.

## Tóm tắt một dòng
Toán tử "AND" trong C++ là toán tử logic `&&` dùng để kiểm tra tính đúng đắn của nhiều điều kiện cùng lúc, trả về true chỉ khi tất cả các điều kiện đều đúng.