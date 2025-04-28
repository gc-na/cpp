<!--
Meta Description: # Từ Khóa "virtual" trong C++ ## Tóm Tắt Trong C++, từ khóa `virtual` được sử dụng để khai báo các phương thức ảo trong lớp cơ sở, cho phép các lớp dẫ...
Meta Keywords: phương, thức, một, trong, lớp
-->

# Từ Khóa "virtual" trong C++

## Tóm Tắt
Trong C++, từ khóa `virtual` được sử dụng để khai báo các phương thức ảo trong lớp cơ sở, cho phép các lớp dẫn xuất ghi đè và cung cấp hành vi tùy chỉnh cho các phương thức này.

## Tài Liệu
Từ khóa `virtual` là một phần quan trọng trong lập trình hướng đối tượng trong C++. Nó cho phép bạn định nghĩa các phương thức có thể được ghi đè (override) trong các lớp dẫn xuất. Khi một phương thức được khai báo là ảo, C++ sẽ sử dụng cơ chế gọi động (dynamic dispatch) để xác định phương thức nào sẽ được gọi vào thời điểm chạy, thay vì tại thời điểm biên dịch.

### Mục Đích
Mục đích chính của từ khóa `virtual` là hỗ trợ tính kế thừa và đa hình trong C++. Điều này cho phép các đối tượng của lớp dẫn xuất được sử dụng một cách linh hoạt hơn trong các ngữ cảnh mà lớp cơ sở được yêu cầu.

### Cách Sử Dụng
Để khai báo một phương thức là ảo, chỉ cần thêm từ khóa `virtual` trước định nghĩa của phương thức trong lớp cơ sở. Ví dụ:

```cpp
class Base {
public:
    virtual void display() {
        cout << "Display from Base class" << endl;
    }
};
```

Trong lớp dẫn xuất, bạn có thể ghi đè phương thức này:

```cpp
class Derived : public Base {
public:
    void display() override { // override là một từ khóa giúp kiểm tra tính hợp lệ
        cout << "Display from Derived class" << endl;
    }
};
```

Khi bạn gọi phương thức `display` trên một con trỏ đến lớp cơ sở nhưng trỏ đến một đối tượng của lớp dẫn xuất, phương thức của lớp dẫn xuất sẽ được gọi:

```cpp
Base* b = new Derived();
b->display(); // Kết quả: "Display from Derived class"
```

## Ví Dụ
### Ví Dụ 1: Khai báo và sử dụng phương thức ảo

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void sound() {
        cout << "Some generic animal sound" << endl;
    }
};

class Dog : public Animal {
public:
    void sound() override {
        cout << "Bark" << endl;
    }
};

int main() {
    Animal* myDog = new Dog();
    myDog->sound(); // Kết quả: "Bark"
    delete myDog;
    return 0;
}
```

### Ví Dụ 2: Sử dụng phương thức ảo trong một ngữ cảnh thực tế

```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual void area() = 0; // Phương thức ảo thuần túy
};

class Circle : public Shape {
private:
    double radius;
public:
    Circle(double r) : radius(r) {}
    void area() override {
        cout << "Area of Circle: " << 3.14 * radius * radius << endl;
    }
};

int main() {
    Shape* shape = new Circle(5);
    shape->area(); // Kết quả: "Area of Circle: 78.5"
    delete shape;
    return 0;
}
```

## Giải Thích
Một số vấn đề thường gặp khi làm việc với từ khóa `virtual` bao gồm:

- **Phương thức ảo thuần túy:** Khi bạn khai báo một phương thức ảo mà không có thân hàm, bạn tạo ra một phương thức ảo thuần túy. Điều này bắt buộc các lớp dẫn xuất phải ghi đè phương thức đó.
  
- **Bảng hàm ảo:** C++ sử dụng bảng hàm ảo (vtable) để quản lý các phương thức ảo. Mỗi lớp có phương thức ảo sẽ có một bảng hàm ảo riêng, và mỗi đối tượng của lớp đó sẽ chứa một con trỏ tới bảng hàm ảo tương ứng.

- **Hiệu suất:** Sử dụng phương thức ảo có thể làm giảm hiệu suất do việc gọi động. Tuy nhiên, điều này thường không đáng kể trong hầu hết các ứng dụng.

## Tóm Tắt Một Câu
Từ khóa `virtual` trong C++ cho phép định nghĩa các phương thức ảo, hỗ trợ tính kế thừa và đa hình, giúp tạo ra mã linh hoạt và dễ bảo trì.