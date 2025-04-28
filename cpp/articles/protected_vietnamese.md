<!--
Meta Description: # Từ Khóa "protected" Trong C++: Sự Bảo Vệ Dữ Liệu Trong Lập Trình Hướng Đối Tượng ## Tóm Tắt Từ khóa `protected` trong C++ được sử dụng để chỉ định q...
Meta Keywords: các, lớp, protected, truy, cập
-->

# Từ Khóa "protected" Trong C++: Sự Bảo Vệ Dữ Liệu Trong Lập Trình Hướng Đối Tượng

## Tóm Tắt
Từ khóa `protected` trong C++ được sử dụng để chỉ định quyền truy cập cho các thành viên của lớp, cho phép các lớp con (subclasses) truy cập vào các thành viên đó trong khi vẫn giữ bí mật với các đối tượng bên ngoài.

## Tài Liệu
### Mục Đích
Từ khóa `protected` là một trong ba mức độ truy cập trong C++ (cùng với `public` và `private`). Nó giúp kiểm soát quyền truy cập vào các thành viên của lớp, đảm bảo rằng chỉ có lớp cha và các lớp con có thể truy cập trực tiếp đến các thành viên được đánh dấu là `protected`.

### Cách Sử Dụng
Khi bạn khai báo một thành viên (biến hoặc hàm) là `protected`, bạn sử dụng từ khóa `protected` trước khai báo đó. Ví dụ:

```cpp
class Base {
protected:
    int protectedVar;
    
    void protectedMethod() {
        // Thực hiện một số thao tác
    }
};

class Derived : public Base {
public:
    void accessBase() {
        protectedVar = 10; // Truy cập thành công
        protectedMethod();  // Truy cập thành công
    }
};
```

### Chi Tiết
- **Lớp Cha và Lớp Con**: Các thành viên `protected` có thể được truy cập trong lớp cha và từ các lớp con kế thừa từ lớp cha đó.
- **Không Truy Cập Từ Ngoài**: Các thành viên `protected` không thể được truy cập trực tiếp từ các đối tượng của lớp cha hoặc lớp con bên ngoài.
- **Kế Thừa Đa Cấp**: Trong kế thừa đa cấp, thành viên `protected` vẫn có thể được truy cập từ lớp con ở các cấp độ khác nhau.

## Ví Dụ
### Ví Dụ Cơ Bản
```cpp
#include <iostream>
using namespace std;

class Animal {
protected:
    string name;
public:
    Animal(string n) : name(n) {}
};

class Dog : public Animal {
public:
    Dog(string n) : Animal(n) {}
    void bark() {
        cout << "Woof! My name is " << name << endl; // Truy cập thành viên protected
    }
};

int main() {
    Dog dog("Buddy");
    dog.bark(); // Kết quả: "Woof! My name is Buddy"
    return 0;
}
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Nhầm Lẫn Giữa protected và private**: Cần lưu ý rằng `protected` cho phép truy cập từ các lớp con, trong khi `private` không cho phép điều này.
- **Kế Thừa Đúng Cách**: Đảm bảo rằng các lớp con kế thừa đúng cách nếu bạn muốn sử dụng thành viên `protected`. Nếu kế thừa sai kiểu, quyền truy cập có thể không được duy trì.

## Tóm Tắt Một Dòng
Từ khóa `protected` trong C++ cho phép các lớp con truy cập vào các thành viên của lớp cha, giữ cho chúng không bị truy cập từ các đối tượng bên ngoài.