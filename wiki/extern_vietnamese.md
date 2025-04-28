<!--
Meta Description: # Từ Khóa "extern" trong C++ ## Tóm Tắt Từ khóa `extern` trong C++ được sử dụng để khai báo rằng một biến hoặc hàm được định nghĩa ở một nơi khác, thư...
Meta Keywords: báo, extern, khai, biến, hàm
-->

# Từ Khóa "extern" trong C++

## Tóm Tắt
Từ khóa `extern` trong C++ được sử dụng để khai báo rằng một biến hoặc hàm được định nghĩa ở một nơi khác, thường là trong một tệp nguồn khác. Điều này cho phép chia sẻ và sử dụng các biến và hàm giữa các tệp khác nhau trong một chương trình.

## Tài Liệu
### Mục Đích
Từ khóa `extern` giúp lập trình viên thông báo cho trình biên dịch rằng biến hoặc hàm sẽ được định nghĩa ở một nơi khác, cho phép sử dụng chúng mà không cần định nghĩa lại.

### Cách Sử Dụng
- **Khai báo biến:** Khi khai báo một biến với `extern`, bạn chỉ định rằng biến đó được định nghĩa ở một tệp khác.
- **Khai báo hàm:** Tương tự, bạn có thể sử dụng `extern` để thông báo rằng một hàm được định nghĩa bên ngoài tệp hiện tại.

### Cú Pháp
```cpp
extern type variableName; // Khai báo biến
extern returnType functionName(parameters); // Khai báo hàm
```

## Ví Dụ
### Ví Dụ 1: Khai báo biến
**Tệp A.cpp**
```cpp
#include <iostream>
using namespace std;

int globalVariable = 10; // Định nghĩa biến toàn cục

int main() {
    cout << "Giá trị của globalVariable: " << globalVariable << endl;
    return 0;
}
```

**Tệp B.cpp**
```cpp
#include <iostream>
using namespace std;

extern int globalVariable; // Khai báo biến toàn cục từ A.cpp

int main() {
    cout << "Giá trị của globalVariable từ B: " << globalVariable << endl;
    return 0;
}
```

### Ví Dụ 2: Khai báo hàm
**Tệp A.cpp**
```cpp
#include <iostream>
using namespace std;

void printMessage() { // Định nghĩa hàm
    cout << "Hello from A!" << endl;
}
```

**Tệp B.cpp**
```cpp
#include <iostream>
using namespace std;

extern void printMessage(); // Khai báo hàm từ A.cpp

int main() {
    printMessage(); // Gọi hàm từ A.cpp
    return 0;
}
```

## Giải Thích
### Những Lỗi Thường Gặp
- **Quên định nghĩa:** Nếu bạn khai báo một biến hoặc hàm với `extern` mà không có định nghĩa tương ứng trong bất kỳ tệp nào, chương trình sẽ gặp lỗi khi biên dịch.
- **Khai báo sai kiểu:** Đảm bảo rằng kiểu dữ liệu trong khai báo `extern` phải khớp với kiểu trong định nghĩa.

### Lưu Ý Thêm
- `extern` có thể được sử dụng với các biến toàn cục và hàm, nhưng không thể sử dụng với các biến cục bộ.
- Sử dụng `extern "C"` khi làm việc với các thư viện C để ngăn chặn việc thay đổi tên hàm do biên dịch viên (name mangling).

## Tóm Tắt Một Dòng
Từ khóa `extern` trong C++ cho phép khai báo biến và hàm được định nghĩa ở tệp khác, giúp chia sẻ và tổ chức mã nguồn hiệu quả hơn.