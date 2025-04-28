<!--
Meta Description: # Từ Khóa "private" trong C++: Kiểm Soát Truy Cập Trong Lập Trình Hướng Đối Tượng ## Tóm Tắt Từ khóa `private` trong C++ được sử dụng để xác định mức ...
Meta Keywords: private, viên, truy, cập, lớp
-->

# Từ Khóa "private" trong C++: Kiểm Soát Truy Cập Trong Lập Trình Hướng Đối Tượng

## Tóm Tắt
Từ khóa `private` trong C++ được sử dụng để xác định mức độ truy cập cho các thành viên của lớp, giúp bảo vệ dữ liệu và phương thức khỏi việc truy cập không mong muốn từ bên ngoài lớp.

## Tài Liệu
### Mục Đích
`private` là một trong ba mức độ truy cập trong C++, bao gồm `public`, `protected`, và `private`. Khi một thành viên của lớp được khai báo là `private`, nó chỉ có thể được truy cập và sử dụng từ bên trong lớp đó, điều này cho phép lập trình viên kiểm soát tốt hơn cách thức mà dữ liệu và phương thức được tương tác.

### Cách Sử Dụng
Để khai báo một thành viên là `private`, bạn chỉ cần sử dụng từ khóa `private` trước phần khai báo của các thành viên đó trong lớp. Dưới đây là cú pháp cơ bản:

```cpp
class TênLớp {
private:
    // Thành viên private
    int bienRiengTu;

public:
    // Phương thức công khai để truy cập biến private
    void setBienRiengTu(int giaTri) {
        bienRiengTu = giaTri;
    }

    int getBienRiengTu() {
        return bienRiengTu;
    }
};
```

### Chi Tiết
- Các thành viên `private` không thể được truy cập từ bên ngoài lớp, điều này giúp bảo vệ dữ liệu nhạy cảm và đảm bảo rằng các quy tắc của lớp được tuân thủ.
- `private` thành viên có thể được truy cập thông qua các phương thức công khai (public methods), là một phần của nguyên tắc ẩn giấu thông tin (data hiding).
- Nếu không có khai báo truy cập nào được chỉ định, các thành viên trong lớp sẽ mặc định là `private` nếu lớp đó là lớp bình thường (không phải lớp kế thừa).

## Ví Dụ
### Ví dụ 1: Sử Dụng Từ Khóa `private`
```cpp
#include <iostream>
using namespace std;

class TaiKhoan {
private:
    string tenTaiKhoan;

public:
    void setTenTaiKhoan(string ten) {
        tenTaiKhoan = ten;
    }

    string getTenTaiKhoan() {
        return tenTaiKhoan;
    }
};

int main() {
    TaiKhoan tk;
    tk.setTenTaiKhoan("user123");
    cout << "Tên tài khoản: " << tk.getTenTaiKhoan() << endl;
    return 0;
}
```

### Ví dụ 2: Không Thể Truy Cập Thành Viên `private` Từ Ngoài
```cpp
#include <iostream>
using namespace std;

class SoLuong {
private:
    int so;

public:
    SoLuong(int s) : so(s) {}
};

int main() {
    SoLuong sl(5);
    // sl.so = 10; // Lỗi: không thể truy cập thành viên private
    return 0;
}
```

## Giải Thích
- Một số lập trình viên mới có thể gặp khó khăn trong việc hiểu rằng các thành viên `private` không thể được truy cập trực tiếp từ bên ngoài lớp. Điều này có thể dẫn đến lỗi biên dịch nếu họ cố gắng truy cập chúng.
- Để sử dụng các thành viên `private`, lập trình viên cần phải cung cấp các phương thức công khai để tương tác với chúng.
- Một số lập trình viên có thể nhầm lẫn giữa `protected` và `private`. Trong khi `protected` cho phép lớp con kế thừa truy cập, `private` thì không.

## Tóm Tắt Một Dòng
Từ khóa `private` trong C++ cho phép lập trình viên bảo vệ dữ liệu và phương thức trong lớp, chỉ cho phép truy cập từ bên trong lớp đó.