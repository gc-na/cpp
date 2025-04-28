<!--
Meta Description: # Lớp (Class) trong C++ ## Tóm tắt Lớp (class) trong C++ là một cấu trúc dữ liệu cho phép tổ chức và quản lý dữ liệu theo cách hướng đối tượng, bao gồ...
Meta Keywords: lớp, các, public, class, cho
-->

# Lớp (Class) trong C++

## Tóm tắt
Lớp (class) trong C++ là một cấu trúc dữ liệu cho phép tổ chức và quản lý dữ liệu theo cách hướng đối tượng, bao gồm các thuộc tính và phương thức.

## Tài liệu
### Mục đích
Lớp là khái niệm cơ bản trong lập trình hướng đối tượng (OOP) trong C++. Nó cho phép lập trình viên nhóm các dữ liệu và chức năng liên quan lại với nhau, từ đó tạo ra các đối tượng (object) mà có thể tương tác với nhau.

### Cú pháp
Cú pháp cơ bản để định nghĩa một lớp trong C++ như sau:

```cpp
class TenLop {
public:
    // Thuộc tính
    int thuocTinh;

    // Phương thức
    void ham() {
        // Thực thi mã
    }
};
```

### Sử dụng
- **Khởi tạo đối tượng**: Để sử dụng lớp, bạn cần tạo một đối tượng từ lớp đó.
  
```cpp
TenLop obj;
obj.thuocTinh = 10;
obj.ham();
```

- **Phân cấp truy cập**: C++ hỗ trợ các mức truy cập `public`, `private`, và `protected` để kiểm soát quyền truy cập vào các thuộc tính và phương thức của lớp.

### Chi tiết
- **Constructor và Destructor**: Bạn có thể định nghĩa các hàm khởi tạo (constructor) và hủy (destructor) để quản lý tài nguyên.

```cpp
class TenLop {
public:
    TenLop() { /* khởi tạo */ }
    ~TenLop() { /* hủy */ }
};
```

- **Kế thừa**: C++ hỗ trợ kế thừa, cho phép một lớp con kế thừa thuộc tính và phương thức từ lớp cha.

```cpp
class LopCha {
public:
    void hamCha() { /* ... */ }
};

class LopCon : public LopCha {
public:
    void hamCon() { /* ... */ }
};
```

## Ví dụ
### Ví dụ 1: Định nghĩa và sử dụng lớp đơn giản

```cpp
#include <iostream>
using namespace std;

class HinhTron {
public:
    float banKinh;

    HinhTron(float r) : banKinh(r) {}

    float dienTich() {
        return 3.14 * banKinh * banKinh;
    }
};

int main() {
    HinhTron hinhTron(5);
    cout << "Diện tích hình tròn: " << hinhTron.dienTich() << endl;
    return 0;
}
```

### Ví dụ 2: Lớp với kế thừa

```cpp
#include <iostream>
using namespace std;

class DongVat {
public:
    void keu() {
        cout << "Tiếng kêu động vật" << endl;
    }
};

class Cho : public DongVat {
public:
    void keu() {
        cout << "Gâu gâu" << endl;
    }
};

int main() {
    Cho cho;
    cho.keu(); // Gọi phương thức từ lớp con
    return 0;
}
```

## Giải thích
### Những cạm bẫy thường gặp
- **Quên định nghĩa constructor**: Nếu không định nghĩa constructor, C++ sẽ tạo constructor mặc định, nhưng nếu lớp có các thuộc tính không khởi tạo, điều này có thể dẫn đến lỗi.
- **Truy cập không hợp lệ**: Sử dụng các thuộc tính `private` mà không thông qua phương thức công khai có thể gây ra lỗi biên dịch.

### Ghi chú thêm
- **Khái niệm về lớp tĩnh**: Lớp có thể chứa các thuộc tính và phương thức tĩnh, cho phép truy cập mà không cần tạo đối tượng.

## Tóm tắt một dòng
Lớp trong C++ là một cấu trúc cho phép tổ chức dữ liệu và chức năng theo cách hướng đối tượng, tạo ra các đối tượng có khả năng tương tác với nhau.