<!--
Meta Description: # Namespace trong C++ ## Tóm tắt Namespace trong C++ là một cơ chế giúp tổ chức mã nguồn và tránh xung đột tên giữa các phần của chương trình. ## Tài ...
Meta Keywords: namespace, dụng, trong, các, bạn
-->

# Namespace trong C++

## Tóm tắt
Namespace trong C++ là một cơ chế giúp tổ chức mã nguồn và tránh xung đột tên giữa các phần của chương trình.

## Tài liệu
Namespace được giới thiệu trong C++ để giúp lập trình viên quản lý tên biến, hàm, lớp, và các thực thể khác mà không gây ra xung đột. Khi bạn định nghĩa một namespace, bạn có thể nhóm các phần tử liên quan lại với nhau. Điều này đặc biệt hữu ích trong các dự án lớn hoặc khi sử dụng nhiều thư viện bên ngoài.

### Cú pháp
Để định nghĩa một namespace, bạn sử dụng cú pháp sau:

```cpp
namespace tên_namespace {
    // Định nghĩa biến, hàm, lớp ở đây
}
```

Để sử dụng các phần tử trong namespace, bạn có thể sử dụng toán tử `::` hoặc từ khóa `using`. Ví dụ:

```cpp
namespace MyNamespace {
    void myFunction() {
        // Thực hiện một cái gì đó
    }
}

// Sử dụng toán tử ::
MyNamespace::myFunction();

// Hoặc sử dụng từ khóa using
using MyNamespace::myFunction;
myFunction();
```

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng namespace trong C++:

```cpp
#include <iostream>

namespace Math {
    int add(int a, int b) {
        return a + b;
    }

    int subtract(int a, int b) {
        return a - b;
    }
}

int main() {
    std::cout << "Tổng: " << Math::add(5, 3) << std::endl;
    std::cout << "Hiệu: " << Math::subtract(5, 3) << std::endl;
    return 0;
}
```

## Giải thích
Khi sử dụng namespace, người lập trình cần lưu ý một số điểm sau:

1. **Xung đột tên**: Nếu bạn định nghĩa hai hàm có cùng tên trong các namespace khác nhau, bạn có thể gọi chúng bằng cách sử dụng toán tử `::`. Điều này giúp tránh xung đột tên.

2. **Namespace lồng**: Bạn có thể định nghĩa namespace lồng nhau. Ví dụ:

    ```cpp
    namespace Outer {
        namespace Inner {
            void myFunction() {
                // Thực hiện một cái gì đó
            }
        }
    }
    ```

3. **Sử dụng từ khóa `using`**: Khi bạn sử dụng từ khóa `using`, tất cả các phần tử trong namespace đó sẽ được sử dụng mà không cần phải khai báo namespace trước. Tuy nhiên, điều này có thể gây ra xung đột nếu có các thành phần trùng tên.

4. **Namespace toàn cầu**: Nếu bạn không sử dụng bất kỳ namespace nào, các thành phần bạn định nghĩa sẽ thuộc về namespace toàn cầu. 

## Tóm tắt một dòng
Namespace trong C++ giúp tổ chức mã nguồn và tránh xung đột tên giữa các phần tử trong chương trình.