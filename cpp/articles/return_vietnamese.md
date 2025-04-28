<!--
Meta Description: # Lệnh "return" trong C++: Cách Sử Dụng và Ý Nghĩa ## Tóm tắt Lệnh "return" trong C++ được sử dụng để trả về giá trị từ một hàm, đồng thời kết thúc qu...
Meta Keywords: hàm, return, lệnh, trả, một
-->

# Lệnh "return" trong C++: Cách Sử Dụng và Ý Nghĩa

## Tóm tắt
Lệnh "return" trong C++ được sử dụng để trả về giá trị từ một hàm, đồng thời kết thúc quá trình thực thi của hàm đó. Đây là một phần quan trọng trong việc lập trình hàm, giúp chuyển giá trị từ hàm về cho hàm gọi.

## Tài liệu
Lệnh "return" có vai trò quan trọng trong C++, cho phép lập trình viên xác định giá trị mà hàm sẽ trả về sau khi thực hiện xong các lệnh bên trong hàm. Khi lệnh "return" được thực thi, nó không chỉ trả về giá trị mà còn dừng lại việc thực thi của hàm. Cú pháp cơ bản của lệnh "return" như sau:

```cpp
return expression;
```

- **expression**: Đây có thể là một giá trị, biến, hoặc biểu thức. Kiểu dữ liệu của biểu thức phải tương thích với kiểu dữ liệu được định nghĩa cho hàm.

### Sử dụng
- Được sử dụng trong bất kỳ hàm nào yêu cầu trả về giá trị, ngoại trừ hàm có kiểu trả về là `void`.
- Có thể sử dụng để trả về nhiều loại dữ liệu khác nhau như số nguyên, số thực, chuỗi, và kiểu dữ liệu người dùng định nghĩa.

## Ví dụ
1. Ví dụ đơn giản về hàm trả về một số nguyên:

```cpp
#include <iostream>
using namespace std;

int add(int a, int b) {
    return a + b; // Trả về tổng của a và b
}

int main() {
    cout << "Tổng là: " << add(5, 10) << endl; // Kết quả: Tổng là: 15
    return 0;
}
```

2. Ví dụ về hàm trả về một chuỗi:

```cpp
#include <iostream>
#include <string>
using namespace std;

string greet(string name) {
    return "Xin chào, " + name + "!"; // Trả về lời chào
}

int main() {
    cout << greet("An") << endl; // Kết quả: Xin chào, An!
    return 0;
}
```

## Giải thích
- **Cảnh báo**: Nếu một hàm có kiểu trả về khác với `void` nhưng không có lệnh "return", trình biên dịch sẽ phát sinh lỗi.
- **Nhiều lệnh return**: Một hàm có thể có nhiều lệnh "return". Tuy nhiên, chỉ một lệnh sẽ được thực thi, khi một lệnh "return" được gọi, hàm sẽ kết thúc.
- **Lệnh return không bắt buộc**: Trong hàm có kiểu `void`, không cần sử dụng lệnh "return", nhưng nếu cần thiết, có thể có lệnh "return;" không có biểu thức để thoát khỏi hàm.

## Tóm tắt một dòng
Lệnh "return" trong C++ cho phép trả về giá trị từ hàm và kết thúc quá trình thực thi của hàm đó.