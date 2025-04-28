<!--
Meta Description: # Tìm Hiểu Về Struct Trong C++: Cấu Trúc Dữ Liệu Quan Trọng ## Tóm Tắt `struct` trong C++ là một cách để định nghĩa một kiểu dữ liệu tùy chỉnh, cho ph...
Meta Keywords: struct, các, liệu, một, định
-->

# Tìm Hiểu Về Struct Trong C++: Cấu Trúc Dữ Liệu Quan Trọng

## Tóm Tắt
`struct` trong C++ là một cách để định nghĩa một kiểu dữ liệu tùy chỉnh, cho phép nhóm nhiều biến khác nhau thành một đơn vị duy nhất. Đây là một phương pháp mạnh mẽ để tổ chức và xử lý dữ liệu trong lập trình hướng đối tượng.

## Tài Liệu
### Mục Đích
`struct` được sử dụng để tạo ra các cấu trúc dữ liệu có thể chứa nhiều loại dữ liệu khác nhau. Điều này giúp lập trình viên dễ dàng quản lý và truyền tải thông tin giữa các phần của chương trình.

### Cách Sử Dụng
Để định nghĩa một `struct`, bạn sử dụng từ khóa `struct`, theo sau là tên của cấu trúc và một khối chứa các thành viên (biến).

```cpp
struct TenStruct {
    kiểuDữLiệu thànhViên1;
    kiểuDữLiệu thànhViên2;
    // ...
};
```

Sau khi định nghĩa, bạn có thể tạo các biến của kiểu `struct` như sau:

```cpp
TenStruct tenCauTruc;
tenCauTruc.thànhViên1 = giáTrị1;
tenCauTruc.thànhViên2 = giáTrị2;
```

### Chi Tiết
- `struct` mặc định có tính chất truy cập là `public`, khác với `class` có tính chất mặc định là `private`.
- Bạn có thể định nghĩa các hàm bên trong `struct`, cho phép thực hiện các thao tác trực tiếp trên dữ liệu của nó.
- Các `struct` có thể được sử dụng trong các lớp (class) và có thể kế thừa lẫn nhau.

## Ví Dụ
### Ví dụ Cơ Bản
```cpp
#include <iostream>
using namespace std;

// Định nghĩa một struct
struct SinhVien {
    string ten;
    int tuoi;
};

int main() {
    // Tạo một biến thuộc kiểu SinhVien
    SinhVien sv;
    sv.ten = "Nguyen Van A";
    sv.tuoi = 20;

    // In ra thông tin
    cout << "Ten: " << sv.ten << ", Tuoi: " << sv.tuoi << endl;
    return 0;
}
```

### Ví dụ với Hàm
```cpp
#include <iostream>
using namespace std;

struct HinhChuNhat {
    int chieuDai;
    int chieuRong;

    // Hàm để tính diện tích
    int tinhDienTich() {
        return chieuDai * chieuRong;
    }
};

int main() {
    HinhChuNhat hcn;
    hcn.chieuDai = 5;
    hcn.chieuRong = 4;

    cout << "Dien Tich: " << hcn.tinhDienTich() << endl;
    return 0;
}
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Không Đặt Tên Trùng**: Tránh việc sử dụng tên biến trùng với tên của `struct` hoặc các kiểu dữ liệu khác để tránh nhầm lẫn.
- **Truy Cập Sai**: Do các thành viên của `struct` có tính chất truy cập mặc định là `public`, bạn cần chú ý bảo mật khi làm việc với dữ liệu nhạy cảm.
- **Sử Dụng Kế Thừa**: Khi kế thừa từ `struct`, bạn cần lưu ý về tính chất truy cập để đảm bảo các thành viên được kế thừa đúng cách.

## Tóm Tắt Một Dòng
`struct` trong C++ cho phép lập trình viên định nghĩa các kiểu dữ liệu tùy chỉnh để tổ chức và quản lý dữ liệu hiệu quả.