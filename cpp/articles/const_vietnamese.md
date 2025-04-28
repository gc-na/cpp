<!--
Meta Description: # Từ Khóa `const` trong C++ ## Tóm tắt Từ khóa `const` trong C++ được sử dụng để định nghĩa các biến, tham số hàm, và phương thức mà không cho phép th...
Meta Keywords: const, thay, đổi, không, trỏ
-->

# Từ Khóa `const` trong C++

## Tóm tắt
Từ khóa `const` trong C++ được sử dụng để định nghĩa các biến, tham số hàm, và phương thức mà không cho phép thay đổi giá trị của chúng sau khi đã được khởi tạo. Việc sử dụng `const` giúp cải thiện độ an toàn của mã nguồn và tăng tính rõ ràng trong lập trình.

## Tài liệu
### Mục đích
Từ khóa `const` được sử dụng để chỉ định rằng một biến, tham số hoặc phương thức không thể bị thay đổi trong suốt vòng đời của nó. Điều này có ý nghĩa quan trọng trong việc bảo vệ dữ liệu và tránh các lỗi tiềm ẩn trong quá trình phát triển phần mềm.

### Cách sử dụng
1. **Biến `const`:**
   ```cpp
   const int x = 10;
   // x không thể thay đổi giá trị sau khi được khởi tạo
   ```

2. **Tham số hàm `const`:**
   ```cpp
   void printValue(const int value) {
       // value không thể thay đổi trong thân hàm
       std::cout << value << std::endl;
   }
   ```

3. **Phương thức `const`:**
   ```cpp
   class MyClass {
   public:
       void display() const {
           // không thể thay đổi trạng thái của đối tượng
       }
   };
   ```

4. **Con trỏ `const`:**
   ```cpp
   const int* ptr = &x;
   // Giá trị mà ptr trỏ tới không thể thay đổi
   ```

## Ví dụ
```cpp
#include <iostream>

class Example {
public:
    void show() const {
        std::cout << "This is a const method." << std::endl;
    }
};

int main() {
    const int a = 5;
    // a = 10; // sẽ gây lỗi biên dịch

    Example obj;
    obj.show(); // gọi phương thức const

    return 0;
}
```

## Giải thích
### Những cạm bẫy thường gặp
- **Không thể thay đổi giá trị:** Khi một biến được khai báo là `const`, mọi cố gắng thay đổi giá trị của nó sẽ dẫn đến lỗi biên dịch.
- **Tham số không thể thay đổi:** Khi truyền tham số hàm là `const`, bạn không thể thay đổi giá trị của tham số bên trong hàm.
- **`const` và con trỏ:** Cần phân biệt giữa con trỏ `const` và con trỏ trỏ tới `const`. Con trỏ `const` không cho phép thay đổi địa chỉ mà nó trỏ tới, trong khi con trỏ trỏ tới `const` không cho phép thay đổi giá trị mà nó trỏ tới.

### Lưu ý bổ sung
Sử dụng `const` một cách hợp lý giúp mã nguồn trở nên dễ đọc và dễ bảo trì hơn. Nó cũng có thể giúp trình biên dịch tối ưu hóa mã tốt hơn.

## Tóm tắt một dòng
Từ khóa `const` trong C++ được sử dụng để chỉ định rằng giá trị của biến, tham số, hoặc phương thức không thể bị thay đổi sau khi được khởi tạo.