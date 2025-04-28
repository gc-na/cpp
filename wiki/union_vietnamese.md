<!--
Meta Description: # Union trong C++: Cách sử dụng và ứng dụng ## Tóm tắt Union trong C++ là một kiểu dữ liệu đặc biệt cho phép lưu trữ nhiều kiểu dữ liệu khác nhau tron...
Meta Keywords: một, union, dụng, kiểu, thành
-->

# Union trong C++: Cách sử dụng và ứng dụng

## Tóm tắt
Union trong C++ là một kiểu dữ liệu đặc biệt cho phép lưu trữ nhiều kiểu dữ liệu khác nhau trong cùng một vị trí bộ nhớ, giúp tiết kiệm dung lượng khi không cần sử dụng tất cả các kiểu dữ liệu cùng một lúc.

## Tài liệu
Union là một cấu trúc trong C++ cho phép bạn định nghĩa một kiểu dữ liệu có thể chứa nhiều kiểu khác nhau nhưng chỉ có thể sử dụng một kiểu tại một thời điểm. Khi bạn khai báo một union, tất cả các thành viên của union chia sẻ cùng một địa chỉ bộ nhớ, giúp tiết kiệm bộ nhớ so với struct, nơi mà mỗi thành viên có không gian bộ nhớ riêng.

### Cú pháp
```cpp
union UnionName {
    DataType1 member1;
    DataType2 member2;
    // ...
};
```

### Ví dụ
```cpp
#include <iostream>
using namespace std;

union ExampleUnion {
    int intVal;
    float floatVal;
    char charVal;
};

int main() {
    ExampleUnion myUnion;

    myUnion.intVal = 5;
    cout << "Giá trị int: " << myUnion.intVal << endl;

    myUnion.floatVal = 3.14f; // Ghi đè giá trị int
    cout << "Giá trị float: " << myUnion.floatVal << endl;

    myUnion.charVal = 'A'; // Ghi đè giá trị float
    cout << "Giá trị char: " << myUnion.charVal << endl;

    return 0;
}
```

## Giải thích
Khi sử dụng union, cần chú ý rằng chỉ một thành viên trong union có thể được sử dụng tại một thời điểm. Điều này có nghĩa là việc ghi đè một thành viên sẽ làm mất giá trị của thành viên trước đó. Người lập trình cần phải quản lý việc sử dụng thành viên của union một cách cẩn thận.

### Những điều cần lưu ý
- Không nên sử dụng giá trị của một thành viên nếu bạn đã thay đổi thành viên khác mà không khởi tạo lại.
- Union không thể có constructor hoặc destructor, điều này có thể gây khó khăn khi làm việc với các kiểu dữ liệu phức tạp.
- Hãy cẩn thận với việc sử dụng union trong các tình huống mà bạn cần giữ nguyên giá trị của tất cả các thành viên.

## Tóm tắt ngắn gọn
Union trong C++ cho phép lưu trữ nhiều kiểu dữ liệu trong cùng một không gian bộ nhớ, nhưng chỉ có thể sử dụng một kiểu tại một thời điểm.