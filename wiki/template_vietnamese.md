<!--
Meta Description: # Template trong C++: Tất cả những gì bạn cần biết ## Tóm tắt Template trong C++ là một công cụ mạnh mẽ cho phép lập trình viên viết mã tổng quát, có ...
Meta Keywords: template, kiểu, dụng, bạn, cho
-->

# Template trong C++: Tất cả những gì bạn cần biết

## Tóm tắt
Template trong C++ là một công cụ mạnh mẽ cho phép lập trình viên viết mã tổng quát, có thể hoạt động với nhiều kiểu dữ liệu khác nhau mà không cần phải viết lại mã cho từng kiểu. Điều này giúp tăng tính tái sử dụng và giảm thiểu sai sót trong quá trình lập trình.

## Tài liệu
### Mục đích
Template là một tính năng của C++ cho phép bạn định nghĩa các hàm và lớp mà không cần chỉ định kiểu cụ thể. Thay vào đó, bạn sử dụng các tham số kiểu (type parameters) để cho phép hàm hoặc lớp hoạt động với nhiều kiểu dữ liệu khác nhau.

### Cách sử dụng
Có hai loại template chính trong C++:
1. **Template hàm (Function Templates)**: Cho phép bạn tạo các hàm có thể xử lý nhiều kiểu dữ liệu.
2. **Template lớp (Class Templates)**: Cho phép bạn định nghĩa các lớp có thể làm việc với nhiều kiểu dữ liệu.

**Cú pháp cơ bản:**

#### Template hàm
```cpp
template <typename T>
T max(T a, T b) {
    return (a > b) ? a : b;
}
```

#### Template lớp
```cpp
template <typename T>
class MyClass {
public:
    T data;
    MyClass(T d) : data(d) {}
    T getData() { return data; }
};
```

### Chi tiết
- **Khi nào sử dụng**: Bạn nên sử dụng template khi bạn muốn viết mã có thể tái sử dụng cho nhiều kiểu dữ liệu mà không cần phải sao chép và chỉnh sửa lại nhiều lần.
- **Biến thể kiểu**: Bạn có thể sử dụng nhiều tham số kiểu trong một template. Ví dụ: `template <typename T, typename U>`.
- **Khả năng mở rộng**: Template cho phép bạn định nghĩa các hàm và lớp có thể mở rộng dễ dàng mà không làm phức tạp mã nguồn.

## Ví dụ
### Ví dụ sử dụng Template hàm
```cpp
#include <iostream>
using namespace std;

template <typename T>
T max(T a, T b) {
    return (a > b) ? a : b;
}

int main() {
    cout << max(10, 20) << endl;       // Kết quả: 20
    cout << max(10.5, 20.5) << endl;   // Kết quả: 20.5
    return 0;
}
```

### Ví dụ sử dụng Template lớp
```cpp
#include <iostream>
using namespace std;

template <typename T>
class MyClass {
public:
    T data;
    MyClass(T d) : data(d) {}
    T getData() { return data; }
};

int main() {
    MyClass<int> intObj(10);
    cout << intObj.getData() << endl; // Kết quả: 10

    MyClass<string> stringObj("Hello");
    cout << stringObj.getData() << endl; // Kết quả: Hello

    return 0;
}
```

## Giải thích
- **Lỗi phổ biến**: Một trong những lỗi phổ biến khi làm việc với template là không nhất quán kiểu dữ liệu. Nếu bạn sử dụng các kiểu không tương thích, bạn sẽ gặp lỗi biên dịch.
- **Báo cáo lỗi**: Thông báo lỗi khi sử dụng template có thể khá khó hiểu, vì vậy bạn cần chú ý kiểm tra các kiểu dữ liệu được sử dụng trong template.
- **Tối ưu hóa**: Template có thể dẫn đến mã nguồn lớn hơn do việc tạo mã cho từng kiểu cụ thể. Hãy cân nhắc khi sử dụng template cho các ứng dụng lớn.

## Tóm tắt một câu
Template trong C++ là công cụ cho phép bạn viết mã tổng quát và tái sử dụng cho nhiều kiểu dữ liệu khác nhau, giúp giảm thiểu mã nguồn và lỗi.