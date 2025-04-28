<!--
Meta Description: # Từ Khóa "static" trong C++: Tìm Hiểu và Ứng Dụng ## Tóm Tắt Từ khóa `static` trong C++ được sử dụng để định nghĩa các biến và hàm với thời gian sống...
Meta Keywords: static, biến, hàm, được, trong
-->

# Từ Khóa "static" trong C++: Tìm Hiểu và Ứng Dụng

## Tóm Tắt
Từ khóa `static` trong C++ được sử dụng để định nghĩa các biến và hàm với thời gian sống dài và phạm vi sử dụng cụ thể, giúp quản lý bộ nhớ và tăng hiệu suất cho chương trình.

## Tài Liệu
### Mục Đích
`static` cho phép bạn kiểm soát thời gian sống của biến và phạm vi của nó. Biến được khai báo là `static` sẽ không bị hủy khi ra khỏi phạm vi, mà sẽ giữ giá trị của nó cho lần gọi sau.

### Cách Sử Dụng
1. **Biến cục bộ tĩnh**: Khi khai báo một biến cục bộ là `static`, nó sẽ tồn tại trong suốt vòng đời của chương trình, và giá trị của nó sẽ được lưu giữa các lần gọi hàm.
   
   ```cpp
   void function() {
       static int count = 0; // Biến này chỉ được khởi tạo một lần
       count++;
       std::cout << count << std::endl;
   }
   ```

2. **Biến toàn cục tĩnh**: Biến toàn cục được khai báo là `static` chỉ có thể được truy cập trong file mà nó được định nghĩa. Điều này giúp tránh xung đột tên giữa các file khác nhau.

   ```cpp
   static int globalVar = 10; // Chỉ có thể truy cập trong file này
   ```

3. **Hàm tĩnh**: Hàm được khai báo là `static` trong một lớp chỉ có thể được gọi từ các hàm tĩnh khác hoặc từ các đối tượng của lớp đó, và không thể truy cập thông qua một đối tượng.

   ```cpp
   class MyClass {
   public:
       static void staticFunction() {
           std::cout << "Hàm tĩnh được gọi" << std::endl;
       }
   };
   ```

### Chi Tiết
- **Thời gian sống**: Biến `static` tồn tại từ khi chương trình bắt đầu cho đến khi chương trình kết thúc.
- **Phạm vi**: Biến cục bộ `static` có phạm vi trong hàm mà nó được định nghĩa, trong khi biến toàn cục `static` chỉ có thể được truy cập trong file định nghĩa.
- **Hàm tĩnh trong lớp**: Hàm tĩnh không có quyền truy cập vào các thành viên không tĩnh của lớp.

## Ví Dụ
```cpp
#include <iostream>

void demoStatic() {
    static int count = 0; // Biến này sẽ giữ giá trị giữa các lần gọi
    count++;
    std::cout << "Đã gọi hàm " << count << " lần." << std::endl;
}

int main() {
    demoStatic(); // Đầu ra: Đã gọi hàm 1 lần.
    demoStatic(); // Đầu ra: Đã gọi hàm 2 lần.
    demoStatic(); // Đầu ra: Đã gọi hàm 3 lần.
    return 0;
}
```

## Giải Thích
- **Lỗi thường gặp**: Không nên nhầm lẫn giữa biến `static` và biến toàn cục. Biến cục bộ `static` không thể được truy cập ngoài hàm mà nó được định nghĩa.
- **Hiệu suất**: Sử dụng biến `static` có thể cải thiện hiệu suất khi bạn cần lưu trữ giá trị giữa các lần gọi hàm mà không cần phải truyền tham số.
- **Tính đồng nhất**: Khi sử dụng `static` cho biến trong nhiều file, hãy chú ý đến việc quản lý tên để tránh xung đột.

## Tóm Tắt Một Dòng
Từ khóa `static` trong C++ giúp tối ưu hóa quản lý biến bằng cách duy trì giá trị giữa các lần gọi và hạn chế phạm vi sử dụng của biến và hàm.