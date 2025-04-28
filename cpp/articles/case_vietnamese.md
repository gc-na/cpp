<!--
Meta Description: # C++ Case: Cách Sử Dụng Câu Lệnh Switch-Case Trong Lập Trình C++ ## Tóm tắt Câu lệnh `case` trong C++ được sử dụng trong cấu trúc điều kiện `switch` ...
Meta Keywords: case, switch, giá, trị, một
-->

# C++ Case: Cách Sử Dụng Câu Lệnh Switch-Case Trong Lập Trình C++

## Tóm tắt
Câu lệnh `case` trong C++ được sử dụng trong cấu trúc điều kiện `switch` để xác định các nhánh khác nhau mà chương trình có thể thực hiện dựa trên giá trị của một biểu thức.

## Tài liệu
Câu lệnh `case` là một phần của cấu trúc điều kiện `switch`, cho phép lập trình viên kiểm tra một giá trị và thực hiện các hành động khác nhau dựa trên giá trị đó. Cấu trúc cơ bản của `switch-case` bao gồm:

1. **Switch**: Khởi đầu bằng từ khóa `switch`, theo sau là biểu thức cần kiểm tra.
2. **Case**: Mỗi nhánh điều kiện được xác định bằng từ khóa `case`, theo sau là một giá trị cụ thể. Nếu giá trị của biểu thức trong `switch` khớp với giá trị của `case`, đoạn mã đi kèm sẽ được thực thi.
3. **Default**: Tùy chọn, `default` được sử dụng để xử lý trường hợp không khớp với bất kỳ `case` nào.

Cú pháp cơ bản:
```cpp
switch (biểu_thức) {
    case giá_trị_1:
        // đoạn mã thực thi nếu biểu thức khớp với giá_trị_1
        break;
    case giá_trị_2:
        // đoạn mã thực thi nếu biểu thức khớp với giá_trị_2
        break;
    default:
        // đoạn mã thực thi nếu không khớp với bất kỳ giá trị nào
        break;
}
```

## Ví dụ
Dưới đây là một ví dụ đơn giản minh họa cách sử dụng câu lệnh `switch-case`:

```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 3;

    switch (day) {
        case 1:
            cout << "Thứ Hai" << endl;
            break;
        case 2:
            cout << "Thứ Ba" << endl;
            break;
        case 3:
            cout << "Thứ Tư" << endl;
            break;
        default:
            cout << "Ngày không hợp lệ" << endl;
            break;
    }

    return 0;
}
```

Kết quả của chương trình trên sẽ là:
```
Thứ Tư
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng câu lệnh `switch-case`:

- **Không có `break`**: Nếu không có câu lệnh `break` sau mỗi `case`, chương trình sẽ tiếp tục thực thi các nhánh `case` tiếp theo (được gọi là "fall-through"). Điều này có thể không mong muốn trong nhiều trường hợp.
- **Loại dữ liệu**: `switch` chỉ hoạt động với một số kiểu dữ liệu nhất định như `int`, `char`, và `enum`. Nó không hỗ trợ cho các kiểu dữ liệu như `float` hay `string`.
- **Giá trị duy nhất**: Mỗi nhánh `case` cần phải có một giá trị duy nhất. Không thể có hai nhánh `case` với cùng một giá trị.

## Tóm tắt một dòng
Câu lệnh `case` trong C++ được sử dụng trong cấu trúc `switch` để thực hiện các hành động khác nhau dựa trên giá trị của một biểu thức.