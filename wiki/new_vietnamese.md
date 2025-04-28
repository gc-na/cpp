<!--
Meta Description: # Từ Khóa "new" trong C++: Tạo và Quản Lý Bộ Nhớ Động ## Tóm tắt Từ khóa "new" trong C++ được sử dụng để cấp phát bộ nhớ động cho các đối tượng và kiể...
Meta Keywords: nhớ, cấp, phát, new, cho
-->

# Từ Khóa "new" trong C++: Tạo và Quản Lý Bộ Nhớ Động

## Tóm tắt
Từ khóa "new" trong C++ được sử dụng để cấp phát bộ nhớ động cho các đối tượng và kiểu dữ liệu. Cụ thể hơn, nó cho phép lập trình viên tạo ra các đối tượng trên heap, giúp quản lý bộ nhớ một cách linh hoạt và hiệu quả.

## Tài liệu
Từ khóa "new" trong C++ có hai hình thức chính: cấp phát bộ nhớ cho kiểu dữ liệu cơ bản và cấp phát cho các đối tượng của lớp. 

### Cách sử dụng
- **Cấp phát bộ nhớ cho kiểu dữ liệu cơ bản:** 
  ```cpp
  int* ptr = new int; // Cấp phát bộ nhớ cho một số nguyên
  ```
- **Cấp phát cho đối tượng lớp:** 
  ```cpp
  class MyClass {
  public:
      MyClass() { /* constructor */ }
  };
  
  MyClass* obj = new MyClass(); // Cấp phát bộ nhớ cho một đối tượng MyClass
  ```

### Chi tiết
Khi sử dụng từ khóa "new", bộ nhớ sẽ được cấp phát từ heap, khác với stack, và nó sẽ không tự động giải phóng khi ra khỏi phạm vi. Do đó, lập trình viên cần sử dụng "delete" để giải phóng bộ nhớ đã cấp phát. 

Cú pháp của "new" có thể đi kèm với danh sách khởi tạo:
```cpp
int* arr = new int[10]; // Cấp phát bộ nhớ cho một mảng 10 số nguyên
```

## Ví dụ
### Ví dụ 1: Cấp phát bộ nhớ cho kiểu dữ liệu cơ bản
```cpp
#include <iostream>
using namespace std;

int main() {
    int* number = new int(5); // Cấp phát bộ nhớ và khởi tạo giá trị
    cout << *number << endl; // In ra giá trị 5
    delete number; // Giải phóng bộ nhớ
    return 0;
}
```

### Ví dụ 2: Cấp phát cho đối tượng lớp
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    MyClass() {
        cout << "Constructor called!" << endl;
    }
    ~MyClass() {
        cout << "Destructor called!" << endl;
    }
};

int main() {
    MyClass* obj = new MyClass(); // Tạo đối tượng mới
    delete obj; // Giải phóng bộ nhớ
    return 0;
}
```

## Giải thích
Một số lưu ý khi sử dụng từ khóa "new":
- **Quản lý bộ nhớ:** Nếu không sử dụng "delete" sau khi cấp phát bộ nhớ, sẽ xảy ra rò rỉ bộ nhớ, gây ảnh hưởng đến hiệu suất và độ ổn định của chương trình.
- **Cấp phát mảng:** Khi cấp phát mảng bằng "new", bạn phải sử dụng "delete[]" để giải phóng:
  ```cpp
  int* arr = new int[10];
  delete[] arr; // Giải phóng bộ nhớ cho mảng
  ```
- **Khởi tạo không cần thiết:** Cần chú ý không khởi tạo đối tượng nhiều lần mà không giải phóng bộ nhớ trước đó.

## Tóm tắt
Từ khóa "new" trong C++ cho phép lập trình viên cấp phát bộ nhớ động cho kiểu dữ liệu và đối tượng, nhưng cần quản lý bộ nhớ một cách cẩn thận để tránh rò rỉ bộ nhớ.