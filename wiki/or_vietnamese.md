<!--
Meta Description: # Toán Tử "or" trong C++ ## Tóm tắt Toán tử "or" trong C++ là một toán tử logic được sử dụng để thực hiện phép so sánh giữa hai biểu thức, trả về giá ...
Meta Keywords: toán, trong, một, điều, được
-->

# Toán Tử "or" trong C++

## Tóm tắt
Toán tử "or" trong C++ là một toán tử logic được sử dụng để thực hiện phép so sánh giữa hai biểu thức, trả về giá trị `true` nếu ít nhất một trong các biểu thức là đúng.

## Tài liệu
Toán tử "or" là một phần của toán tử logic trong C++, thường được sử dụng để kiểm tra nhiều điều kiện. Toán tử này là một trong những cách viết tắt cho toán tử `||`. Cú pháp cơ bản của toán tử "or" như sau:

```cpp
bool result = expression1 or expression2;
```

### Mục đích
Toán tử "or" cho phép lập trình viên kiểm tra nhiều điều kiện cùng lúc, làm cho mã nguồn trở nên ngắn gọn và dễ đọc hơn.

### Sử dụng
- Toán tử "or" có thể được sử dụng trong các cấu trúc điều kiện như `if`, `while`, hoặc bất kỳ vị trí nào mà một biểu thức boolean được yêu cầu.
- Nó có thể kết hợp với các loại dữ liệu boolean hoặc các biểu thức trả về giá trị boolean.

## Ví dụ
```cpp
#include <iostream>

int main() {
    bool a = true;
    bool b = false;

    // Sử dụng toán tử "or"
    if (a or b) {
        std::cout << "Ít nhất một trong hai điều kiện là đúng." << std::endl;
    } else {
        std::cout << "Cả hai điều kiện đều sai." << std::endl;
    }

    return 0;
}
```

Trong ví dụ trên, do `a` có giá trị `true`, câu lệnh trong khối `if` sẽ được thực thi.

## Giải thích
- **Cách sử dụng**: Khi sử dụng toán tử "or", lập trình viên cần nhớ rằng chỉ cần một trong các biểu thức là đúng thì kết quả sẽ trả về `true`.
- **Lưu ý về hiệu suất**: Trong một số trường hợp, nếu biểu thức đầu tiên đã trả về `true`, biểu thức thứ hai sẽ không được đánh giá (điều này được gọi là "ngắn mạch").
- **Nhầm lẫn với toán tử khác**: Đừng nhầm lẫn toán tử "or" với toán tử "||". Chúng có chức năng tương tự, nhưng "or" là từ khóa trong C++ và có thể dễ đọc hơn trong một số ngữ cảnh.

## Tóm tắt một dòng
Toán tử "or" trong C++ cho phép kiểm tra nhiều điều kiện, trả về `true` nếu ít nhất một trong các điều kiện là đúng.