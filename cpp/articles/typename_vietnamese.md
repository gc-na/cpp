<!--
Meta Description: # Từ Khóa "typename" Trong C++ ## Tóm tắt Từ khóa `typename` trong C++ được sử dụng để chỉ định rằng một tên là một kiểu dữ liệu trong ngữ cảnh của lậ...
Meta Keywords: typename, một, kiểu, trong, liệu
-->

# Từ Khóa "typename" Trong C++

## Tóm tắt
Từ khóa `typename` trong C++ được sử dụng để chỉ định rằng một tên là một kiểu dữ liệu trong ngữ cảnh của lập trình kiểu tổng quát (template). Nó giúp biên dịch viên xác định rõ ràng các kiểu dữ liệu trong các mẫu lớp (class template) và hàm (function template).

## Tài liệu
### Mục đích
`typename` thường được sử dụng trong các template để cho biết rằng một tên có thể là một kiểu dữ liệu. Điều này rất quan trọng khi bạn làm việc với các kiểu dữ liệu chưa được xác định rõ ràng, đặc biệt là khi sử dụng các kiểu dữ liệu lồng nhau.

### Cách sử dụng
Cú pháp cơ bản của `typename` như sau:
```cpp
template <typename T>
void func(T param) {
    // Sử dụng T như một kiểu dữ liệu
}
```

Trong trường hợp bạn cần xác định một kiểu dữ liệu bên trong một template, bạn cũng có thể sử dụng `typename` như sau:
```cpp
template <typename T>
void func(T param) {
    typename T::SubType var; // SubType là một kiểu dữ liệu trong T
}
```

### Chi tiết
- `typename` có thể được sử dụng trong các template để xác định một kiểu dữ liệu mà có thể không được biết đến cho đến lúc biên dịch.
- Nó giúp tránh nhầm lẫn khi có tên trùng lặp, đặc biệt khi làm việc với các kiểu dữ liệu lồng nhau.
- Cần phân biệt giữa `typename` và `class` trong định nghĩa template; cả hai đều có thể được sử dụng nhưng có một số khác biệt nhỏ về ngữ nghĩa.

## Ví dụ
### Ví dụ 1: Sử dụng cơ bản
```cpp
#include <iostream>
using namespace std;

template <typename T>
void print(T value) {
    cout << value << endl;
}

int main() {
    print(10);        // In ra 10
    print(3.14);     // In ra 3.14
    print("Hello");  // In ra Hello
    return 0;
}
```

### Ví dụ 2: Sử dụng trong kiểu lồng nhau
```cpp
#include <iostream>
#include <vector>
using namespace std;

template <typename T>
void processVector(const vector<T>& vec) {
    typename vector<T>::const_iterator it;

    for (it = vec.begin(); it != vec.end(); ++it) {
        cout << *it << " ";
    }
    cout << endl;
}

int main() {
    vector<int> vec = {1, 2, 3, 4, 5};
    processVector(vec); // In ra: 1 2 3 4 5
    return 0;
}
```

## Giải thích
- Một số lập trình viên có thể nhầm lẫn giữa `typename` và từ khóa `class` trong định nghĩa template, nhưng cả hai có thể thay thế cho nhau trong nhiều trường hợp.
- Một số lỗi phổ biến là quên sử dụng `typename` khi truy cập vào các kiểu lồng nhau, dẫn đến lỗi biên dịch.
- `typename` cần thiết khi bạn muốn xác định một kiểu dữ liệu trong các ngữ cảnh mà tên đó có thể được hiểu là một biến hoặc một hàm, không phải là một kiểu.

## Tóm tắt một dòng
Từ khóa `typename` trong C++ giúp xác định rõ ràng các kiểu dữ liệu trong template, đặc biệt là khi làm việc với các kiểu lồng nhau.