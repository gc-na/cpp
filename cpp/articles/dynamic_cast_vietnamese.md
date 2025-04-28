<!--
Meta Description: # dynamic_cast trong C++: Tìm Hiểu và Sử Dụng ## Tóm tắt `dynamic_cast` là một toán tử trong C++ được sử dụng để an toàn chuyển đổi kiểu giữa các lớp ...
Meta Keywords: dynamic_cast, một, chuyển, đổi, std
-->

# dynamic_cast trong C++: Tìm Hiểu và Sử Dụng

## Tóm tắt
`dynamic_cast` là một toán tử trong C++ được sử dụng để an toàn chuyển đổi kiểu giữa các lớp trong một hệ thống kế thừa. Toán tử này giúp xác định kiểu thực của đối tượng tại thời điểm chạy, đảm bảo rằng việc chuyển đổi kiểu là hợp lệ.

## Tài liệu
`dynamic_cast` chủ yếu được sử dụng trong các tình huống liên quan đến kế thừa và đa hình trong C++. Toán tử này cho phép bạn chuyển đổi giữa các con trỏ hoặc tham chiếu của lớp cơ sở và lớp dẫn xuất. Một điểm quan trọng là `dynamic_cast` chỉ hoạt động với các lớp có ít nhất một hàm ảo.

### Cú pháp
```cpp
dynamic_cast<new_type>(expression);
```

- `new_type`: Kiểu mà bạn muốn chuyển đổi tới, phải là một lớp dẫn xuất từ lớp cơ sở.
- `expression`: Biến hoặc con trỏ của lớp cơ sở.

### Trả về
- Nếu chuyển đổi thành công, `dynamic_cast` trả về một giá trị hợp lệ của kiểu `new_type`.
- Nếu không thành công, nếu bạn đang sử dụng con trỏ, nó sẽ trả về `nullptr`. Nếu bạn đang sử dụng tham chiếu, nó sẽ ném ra một ngoại lệ `std::bad_cast`.

## Ví dụ
### Ví dụ 1: Sử dụng với con trỏ
```cpp
#include <iostream>
class Base {
    virtual void foo() {}
};
class Derived : public Base {
    void bar() {}
};

int main() {
    Base* basePtr = new Derived();
    Derived* derivedPtr = dynamic_cast<Derived*>(basePtr);
    
    if (derivedPtr) {
        std::cout << "Chuyển đổi thành công!" << std::endl;
    } else {
        std::cout << "Chuyển đổi thất bại!" << std::endl;
    }

    delete basePtr;
    return 0;
}
```

### Ví dụ 2: Sử dụng với tham chiếu
```cpp
#include <iostream>
class Base {
    virtual void foo() {}
};
class Derived : public Base {
    void bar() {}
};

int main() {
    Base* basePtr = new Derived();
    try {
        Derived& derivedRef = dynamic_cast<Derived&>(*basePtr);
        std::cout << "Chuyển đổi thành công!" << std::endl;
    } catch (std::bad_cast& e) {
        std::cout << "Chuyển đổi thất bại!" << std::endl;
    }

    delete basePtr;
    return 0;
}
```

## Giải thích
- **Cảnh giác với nullptr**: Khi sử dụng `dynamic_cast` với con trỏ, hãy luôn kiểm tra giá trị trả về để tránh dereferencing một con trỏ `nullptr`.
- **Sử dụng tham chiếu**: Nếu bạn sử dụng `dynamic_cast` với tham chiếu, hãy chắc chắn xử lý ngoại lệ `std::bad_cast` để tránh làm chương trình bị sập khi chuyển đổi thất bại.
- **Chỉ dành cho lớp có hàm ảo**: `dynamic_cast` chỉ hoạt động trên các lớp có ít nhất một hàm ảo. Nếu không, nó sẽ không biết kiểu thực của đối tượng.

## Tóm tắt một dòng
`dynamic_cast` là một toán tử trong C++ cho phép chuyển đổi an toàn giữa các kiểu trong hệ thống kế thừa, đảm bảo tính đúng đắn của các đối tượng trong thời gian chạy.