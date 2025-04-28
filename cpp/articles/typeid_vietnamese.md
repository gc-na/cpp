<!--
Meta Description: # Sử Dụng `typeid` Trong C++: Tính Năng Xác Định Kiểu Dữ Liệu ## Tóm Tắt `typeid` là một toán tử trong C++ cho phép xác định kiểu của một đối tượng tạ...
Meta Keywords: kiểu, typeid, một, của, dụng
-->

# Sử Dụng `typeid` Trong C++: Tính Năng Xác Định Kiểu Dữ Liệu

## Tóm Tắt
`typeid` là một toán tử trong C++ cho phép xác định kiểu của một đối tượng tại thời điểm chạy. Nó hữu ích trong việc kiểm tra kiểu và thực hiện các hành động khác nhau dựa trên kiểu dữ liệu của đối tượng.

## Tài Liệu
### Mục Đích
Toán tử `typeid` được sử dụng để lấy thông tin về kiểu dữ liệu của một đối tượng hoặc kiểu dữ liệu của một biểu thức. Đây là một phần của cơ chế RTTI (Run-Time Type Information) trong C++, cho phép lập trình viên thực hiện kiểm tra kiểu tại thời gian chạy.

### Cách Sử Dụng
Cú pháp của `typeid` như sau:

```cpp
typeid(expression)
```

- **expression**: Biểu thức mà bạn muốn kiểm tra kiểu dữ liệu.

Kết quả của `typeid` là một tham chiếu tới một đối tượng `std::type_info`, cung cấp thông tin về kiểu dữ liệu.

### Chi Tiết
- `typeid` có thể được sử dụng với các loại dữ liệu nguyên thủy, kiểu người dùng, và con trỏ đến lớp.
- Khi dùng với con trỏ đến lớp cơ sở, `typeid` sẽ trả về kiểu thực sự của đối tượng nếu lớp đó có ít nhất một hàm ảo.
- Để sử dụng `typeid`, bạn cần bao gồm thư viện `typeinfo`.

## Ví Dụ
### Ví Dụ Cơ Bản
```cpp
#include <iostream>
#include <typeinfo>

class Base {
    virtual void foo() {}
};

class Derived : public Base {};

int main() {
    Base* b = new Derived;
    std::cout << "Kiểu thực của b: " << typeid(*b).name() << std::endl;
    std::cout << "Kiểu của Base: " << typeid(Base).name() << std::endl;
    delete b;
    return 0;
}
```
### Kết Quả
Kết quả sẽ hiển thị kiểu thực sự của đối tượng `b`, cho thấy rằng nó là một đối tượng của lớp `Derived`.

## Giải Thích
- **Cảnh báo**: Nếu bạn sử dụng `typeid` với một con trỏ không hợp lệ (nullptr), chương trình sẽ ném ra một ngoại lệ `std::bad_typeid`.
- **Tính Năng RTTI**: Để sử dụng `typeid` với các lớp cơ sở, lớp đó cần phải có ít nhất một hàm ảo, nếu không, `typeid` sẽ chỉ trả về kiểu của lớp cơ sở.
- **Tối Ưu Hóa**: Việc sử dụng `typeid` có thể gây ảnh hưởng đến hiệu suất nếu được gọi nhiều lần trong một vòng lặp, vì vậy nên cân nhắc khi sử dụng trong các tình huống nhạy cảm với hiệu suất.

## Tóm Tắt Một Dòng
`typeid` là toán tử trong C++ cho phép xác định kiểu của một đối tượng tại thời điểm chạy, hỗ trợ kiểm tra và quản lý kiểu dữ liệu hiệu quả.