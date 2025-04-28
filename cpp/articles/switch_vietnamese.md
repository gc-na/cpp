<!--
Meta Description: # C++ Switch: Câu lệnh Chọn Lựa trong C++ ## Tóm tắt Câu lệnh `switch` trong C++ là một cấu trúc điều kiện cho phép lập trình viên kiểm tra một biến v...
Meta Keywords: switch, giá, trị, case, break
-->

# C++ Switch: Câu lệnh Chọn Lựa trong C++

## Tóm tắt
Câu lệnh `switch` trong C++ là một cấu trúc điều kiện cho phép lập trình viên kiểm tra một biến với nhiều giá trị khác nhau và thực thi các khối mã tương ứng với giá trị đã cho.

## Tài liệu
Câu lệnh `switch` được sử dụng để lựa chọn giữa nhiều trường hợp khác nhau dựa trên giá trị của một biểu thức. Cú pháp cơ bản của câu lệnh `switch` như sau:

```cpp
switch (biểu_thức) {
    case giá_trị_1:
        // khối mã cho giá trị 1
        break;
    case giá_trị_2:
        // khối mã cho giá trị 2
        break;
    ...
    default:
        // khối mã mặc định nếu không có trường hợp nào khớp
}
```

### Mục đích
- **Đơn giản hóa mã:** Câu lệnh `switch` giúp mã dễ đọc hơn khi kiểm tra nhiều giá trị cho một biến.
- **Hiệu suất:** `switch` có thể nhanh hơn so với nhiều câu lệnh `if-else` trong một số trường hợp nhất định.

### Cách sử dụng
1. **Biểu thức:** Biểu thức trong `switch` phải có kiểu dữ liệu nguyên (integer), ký tự (char) hoặc enum.
2. **Các trường hợp (case):** Mỗi trường hợp trong `switch` được định nghĩa bởi từ khóa `case` và theo sau là giá trị cần kiểm tra.
3. **Khối mã:** Các khối mã tương ứng với mỗi trường hợp sẽ được thực thi nếu giá trị của biểu thức khớp với giá trị đó.
4. **Từ khóa `break`:** Sử dụng `break` để ngăn chặn việc tiếp tục thực thi các trường hợp phía dưới.
5. **Khối mã mặc định:** Tùy chọn `default` được sử dụng để xử lý trường hợp không khớp với bất kỳ `case` nào.

## Ví dụ
### Ví dụ 1: Sử dụng câu lệnh switch cơ bản

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 2;

    switch (x) {
        case 1:
            cout << "Gia tri la 1" << endl;
            break;
        case 2:
            cout << "Gia tri la 2" << endl;
            break;
        case 3:
            cout << "Gia tri la 3" << endl;
            break;
        default:
            cout << "Khong phai gia tri 1, 2, hoac 3" << endl;
    }

    return 0;
}
```

### Ví dụ 2: Không sử dụng `break`

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 1;

    switch (x) {
        case 1:
            cout << "Gia tri la 1" << endl;
        case 2:
            cout << "Gia tri la 2" << endl;
            break;
        default:
            cout << "Khong phai gia tri 1 hoac 2" << endl;
    }

    return 0;
}
```

Kết quả: 
```
Gia tri la 1
Gia tri la 2
```

## Giải thích
### Những cạm bẫy phổ biến
- **Thiếu `break`:** Nếu không sử dụng `break`, chương trình sẽ tiếp tục thực hiện các khối mã của các `case` phía sau, điều này có thể dẫn đến hành vi không mong muốn.
- **Giá trị không khớp:** Nếu không có giá trị nào khớp với biểu thức `switch`, khối mã trong `default` sẽ được thực thi nếu có.

### Lưu ý
- Câu lệnh `switch` không hỗ trợ kiểu dữ liệu số thực (float, double).
- Nên tránh lạm dụng `switch` cho các trường hợp phức tạp với nhiều điều kiện khác nhau mà nên sử dụng `if-else` để tăng tính rõ ràng cho mã nguồn.

## Tóm tắt một dòng
Câu lệnh `switch` trong C++ cho phép kiểm tra giá trị của một biến và thực hiện các khối mã tương ứng với giá trị đó, giúp mã nguồn trở nên rõ ràng và hiệu quả hơn.