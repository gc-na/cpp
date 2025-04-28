<!--
Meta Description: # Toán tử not_eq trong C++ ## Tóm tắt Toán tử `not_eq` trong C++ là một phần của thư viện `<functional>` và được sử dụng để so sánh hai giá trị, trả v...
Meta Keywords: not_eq, bằng, std, trong, một
-->

# Toán tử not_eq trong C++

## Tóm tắt
Toán tử `not_eq` trong C++ là một phần của thư viện `<functional>` và được sử dụng để so sánh hai giá trị, trả về `true` nếu chúng không bằng nhau và `false` nếu chúng bằng nhau. Đây là một cách viết khác của toán tử so sánh không bằng `!=`.

## Tài liệu
Toán tử `not_eq` là một hàm so sánh được định nghĩa trong chuẩn C++ và có thể sử dụng cho nhiều loại kiểu dữ liệu khác nhau. Nó giúp lập trình viên thực hiện các phép so sánh một cách rõ ràng và dễ hiểu hơn, đặc biệt trong các tình huống mà việc sử dụng toán tử truyền thống có thể gây khó khăn về mặt đọc mã.

### Cú pháp
```cpp
#include <functional>

bool not_eq(const T& a, const T& b);
```

### Tham số
- **a**: Giá trị đầu tiên để so sánh.
- **b**: Giá trị thứ hai để so sánh.

### Trả về
Hàm `not_eq` trả về:
- `true`: nếu `a` không bằng `b`.
- `false`: nếu `a` bằng `b`.

### Lưu ý
- `not_eq` có thể được sử dụng cho bất kỳ kiểu dữ liệu nào hỗ trợ toán tử `!=`.
- Việc sử dụng `not_eq` giúp mã nguồn trở nên dễ đọc hơn, đặc biệt trong các biểu thức phức tạp.

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng `not_eq` trong C++:

### Ví dụ 1: So sánh số nguyên
```cpp
#include <iostream>
#include <functional>

int main() {
    int a = 5;
    int b = 10;

    if (not_eq(a, b)) {
        std::cout << "a và b không bằng nhau." << std::endl;
    } else {
        std::cout << "a và b bằng nhau." << std::endl;
    }

    return 0;
}
```

### Ví dụ 2: So sánh chuỗi
```cpp
#include <iostream>
#include <functional>
#include <string>

int main() {
    std::string str1 = "Hello";
    std::string str2 = "World";

    if (not_eq(str1, str2)) {
        std::cout << "str1 và str2 không bằng nhau." << std::endl;
    } else {
        std::cout << "str1 và str2 bằng nhau." << std::endl;
    }

    return 0;
}
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng `not_eq`:
- Sự khác biệt giữa `not_eq` và `!=`: Chúng đều thực hiện cùng một chức năng, nhưng `not_eq` có thể giúp mã nguồn trở nên dễ đọc hơn trong một số trường hợp.
- Hiệu suất: `not_eq` có thể có hiệu suất tương đương với việc sử dụng `!=`, tuy nhiên, nên kiểm tra hiệu suất trong các ứng dụng thực tế nếu bạn làm việc với các kiểu dữ liệu phức tạp.

## Tóm tắt ngắn gọn
Toán tử `not_eq` trong C++ là một hàm so sánh hữu ích để xác định sự không bằng nhau giữa hai giá trị.