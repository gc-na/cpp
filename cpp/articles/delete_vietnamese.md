<!--
Meta Description: # Từ Khóa: "delete trong C++: Cách sử dụng và lưu ý" ## Tóm Tắt `delete` là một toán tử trong C++ được sử dụng để giải phóng bộ nhớ mà đã được cấp phá...
Meta Keywords: delete, nhớ, dụng, cho, giải
-->

# Từ Khóa: "delete trong C++: Cách sử dụng và lưu ý"

## Tóm Tắt
`delete` là một toán tử trong C++ được sử dụng để giải phóng bộ nhớ mà đã được cấp phát động (dynamic memory allocation) bằng các toán tử như `new`. Việc sử dụng `delete` là cần thiết để ngăn ngừa rò rỉ bộ nhớ trong ứng dụng C++.

## Tài Liệu
### Mục Đích
Toán tử `delete` có nhiệm vụ giải phóng bộ nhớ đã được cấp phát cho các đối tượng và mảng trong C++. Điều này giúp quản lý bộ nhớ hiệu quả và tránh tình trạng rò rỉ bộ nhớ, điều có thể dẫn đến hiệu suất kém hoặc sự cố trong chương trình.

### Cách Sử Dụng
Toán tử `delete` có hai dạng chính:
1. **Giải phóng bộ nhớ cho một đối tượng duy nhất:**
   ```cpp
   delete pointer;
   ```

2. **Giải phóng bộ nhớ cho một mảng các đối tượng:**
   ```cpp
   delete[] pointerToArray;
   ```

### Chi Tiết Cách Sử Dụng
- Khi sử dụng `delete`, bạn chỉ nên gọi nó trên các con trỏ mà đã được cấp phát bộ nhớ bằng `new`. Việc gọi `delete` trên một con trỏ không hợp lệ hoặc một con trỏ chưa được cấp phát có thể dẫn đến hành vi không xác định.
- Sau khi sử dụng `delete`, tốt nhất là nên gán lại giá trị cho con trỏ đó thành `nullptr` để tránh việc tham chiếu đến vùng bộ nhớ không hợp lệ.

## Ví Dụ
### Ví dụ 1: Giải phóng bộ nhớ cho một đối tượng
```cpp
#include <iostream>

class MyClass {
public:
    MyClass() { std::cout << "Constructor called" << std::endl; }
    ~MyClass() { std::cout << "Destructor called" << std::endl; }
};

int main() {
    MyClass* obj = new MyClass(); // Cấp phát bộ nhớ cho đối tượng
    delete obj; // Giải phóng bộ nhớ
    return 0;
}
```

### Ví dụ 2: Giải phóng bộ nhớ cho một mảng
```cpp
#include <iostream>

int main() {
    int* arr = new int[5]; // Cấp phát bộ nhớ cho mảng
    delete[] arr; // Giải phóng bộ nhớ cho mảng
    return 0;
}
```

## Giải Thích
Một số lưu ý quan trọng khi sử dụng `delete`:
- **Không gọi `delete` hai lần**: Việc này sẽ dẫn đến lỗi "double free" và có thể gây ra sự cố trong chương trình.
- **Không gọi `delete` trên con trỏ không hợp lệ**: Điều này có thể dẫn đến hành vi không xác định và crash chương trình.
- **Luôn sử dụng `delete[]` với mảng**: Không nên sử dụng `delete` cho mảng đã được cấp phát bằng `new[]`, vì điều này sẽ không gọi destructor cho tất cả các phần tử trong mảng.

## Tóm Tắt Một Dòng
Toán tử `delete` trong C++ được sử dụng để giải phóng bộ nhớ đã được cấp phát cho đối tượng hoặc mảng, giúp ngăn ngừa rò rỉ bộ nhớ trong ứng dụng.