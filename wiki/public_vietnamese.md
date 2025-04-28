<!--
Meta Description: # Từ Khóa "public" Trong C++: Khái Niệm, Cách Sử Dụng và Ví Dụ ## Tóm Tắt Từ khóa "public" trong C++ được sử dụng để xác định mức độ truy cập của các ...
Meta Keywords: public, lớp, truy, cập, trong
-->

# Từ Khóa "public" Trong C++: Khái Niệm, Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Từ khóa "public" trong C++ được sử dụng để xác định mức độ truy cập của các thành viên trong một lớp. Khi một thành viên được khai báo là "public", nó có thể được truy cập từ bất kỳ đâu trong mã nguồn, bao gồm cả các lớp khác và các đối tượng.

## Tài Liệu
Từ khóa "public" là một trong ba mức độ truy cập trong C++, bên cạnh "private" và "protected". Nó cho phép lập trình viên kiểm soát quyền truy cập vào dữ liệu và các phương thức của lớp.

### Mục Đích
Mục đích chính của từ khóa "public" là để cho phép các thành viên của lớp được truy cập tự do từ bên ngoài lớp đó. Điều này rất quan trọng cho việc xây dựng các API (giao diện lập trình ứng dụng) và các lớp mà người dùng có thể tương tác.

### Cách Sử Dụng
Để sử dụng từ khóa "public", bạn chỉ cần khai báo nó trong định nghĩa lớp của bạn, như sau:

```cpp
class MyClass {
public:
    int myPublicVariable;
    void myPublicMethod();
};
```

Trong ví dụ trên, `myPublicVariable` và `myPublicMethod()` có thể được truy cập từ bên ngoài lớp `MyClass`.

### Chi Tiết
- **Mã Nguồn**: Các thành viên "public" có thể được truy cập từ bất kỳ nơi nào trong mã nguồn, miễn là bạn có quyền truy cập đến đối tượng hoặc lớp chứa chúng.
- **Tính Đóng Gói**: Sử dụng "public" giúp các thành viên của lớp có thể được truy cập, nhưng cũng cần chú ý đến tính đóng gói. Bạn nên hạn chế việc lạm dụng quyền truy cập "public" để bảo vệ dữ liệu của lớp.

## Ví Dụ
Dưới đây là một ví dụ đơn giản minh họa cách sử dụng từ khóa "public":

```cpp
#include <iostream>
using namespace std;

class Circle {
public:
    double radius;

    Circle(double r) : radius(r) {}

    double area() {
        return 3.14 * radius * radius;
    }
};

int main() {
    Circle c(5.0);
    cout << "Diện tích hình tròn: " << c.area() << endl; // Kết quả: 78.5
    return 0;
}
```

Trong ví dụ trên, `radius` là một biến công khai và có thể được truy cập từ hàm `main()`.

## Giải Thích
Một số lưu ý quan trọng khi sử dụng từ khóa "public":
- **Lạm Dụng Quyền Truy Cập**: Cần cẩn thận khi khai báo nhiều thành viên là "public", vì điều này có thể làm giảm tính bảo mật và tính ổn định của lớp.
- **Tính Thay Đổi**: Khi bạn thay đổi một thành viên "public", điều này có thể ảnh hưởng đến các phần khác của mã nguồn, đặc biệt nếu lớp đó được sử dụng rộng rãi.
- **Thiết Kế Kiến Trúc**: Nên cân nhắc giữa việc sử dụng "public" và "private" hoặc "protected" để duy trì cấu trúc và tính tổ chức của mã nguồn.

## Tóm Tắt Một Dòng
Từ khóa "public" trong C++ cho phép các thành viên của một lớp được truy cập từ bên ngoài, hỗ trợ tính linh hoạt và khả năng tương tác trong lập trình đối tượng.