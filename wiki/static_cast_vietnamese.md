<!--
Meta Description: # C++ static_cast: Chuyển đổi kiểu an toàn và hiệu quả ## Tóm tắt `static_cast` là một toán tử trong C++ được sử dụng để thực hiện chuyển đổi kiểu an ...
Meta Keywords: kiểu, chuyển, đổi, static_cast, các
-->

# C++ static_cast: Chuyển đổi kiểu an toàn và hiệu quả

## Tóm tắt
`static_cast` là một toán tử trong C++ được sử dụng để thực hiện chuyển đổi kiểu an toàn giữa các kiểu dữ liệu. Nó cho phép lập trình viên chuyển đổi giữa các kiểu con và kiểu cha trong hệ thống phân loại, hoặc giữa các kiểu dữ liệu cơ bản mà không mất dữ liệu.

## Tài liệu
`static_cast` là một trong bốn toán tử chuyển đổi kiểu trong C++, bên cạnh `dynamic_cast`, `const_cast`, và `reinterpret_cast`. Mục đích chính của `static_cast` là cung cấp một cách chuyển đổi kiểu an toàn hơn so với việc sử dụng ép kiểu truyền thống. 

### Cách sử dụng
Cú pháp của `static_cast` như sau:
```cpp
static_cast<kiểu_mới>(biến);
```

- **kiểu_mới**: Kiểu dữ liệu mà bạn muốn chuyển đổi thành.
- **biến**: Biến mà bạn muốn chuyển đổi kiểu.

`static_cast` có thể được sử dụng trong các trường hợp như:
- Chuyển đổi giữa các kiểu dữ liệu số (như từ `int` sang `float`).
- Chuyển đổi giữa các kiểu con và kiểu cha trong hệ thống kế thừa.

### Ví dụ
```cpp
#include <iostream>

class Base {
public:
    virtual void show() { std::cout << "Base class" << std::endl; }
};

class Derived : public Base {
public:
    void show() override { std::cout << "Derived class" << std::endl; }
};

int main() {
    Derived d;
    Base* b = static_cast<Base*>(&d); // Chuyển đổi từ Derived sang Base
    b->show(); // Kết quả: "Derived class"

    int a = 10;
    float f = static_cast<float>(a); // Chuyển đổi từ int sang float
    std::cout << f << std::endl; // Kết quả: 10.0
    return 0;
}
```

## Giải thích
Mặc dù `static_cast` rất hữu ích, nhưng có một số điều cần lưu ý:
- Không thể sử dụng `static_cast` để chuyển đổi giữa các kiểu không liên quan đến nhau (ví dụ: từ một con trỏ kiểu `Base` sang một con trỏ kiểu không phải con).
- `static_cast` không thực hiện kiểm tra an toàn tại thời điểm chạy. Nếu chuyển đổi kiểu không hợp lệ, chương trình có thể dẫn đến hành vi không xác định.
- Đối với các kiểu con và kiểu cha, nếu bạn không chắc chắn về loại thực tế của đối tượng, hãy sử dụng `dynamic_cast` thay vì `static_cast` để đảm bảo an toàn.

## Tóm tắt một dòng
`static_cast` trong C++ cho phép chuyển đổi kiểu an toàn giữa các kiểu dữ liệu, đặc biệt hữu ích trong hệ thống phân loại và chuyển đổi kiểu dữ liệu cơ bản.