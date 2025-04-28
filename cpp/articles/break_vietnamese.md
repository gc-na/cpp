<!--
Meta Description: # C++: Lệnh "break" trong C++ ## Tóm tắt Lệnh "break" trong C++ được sử dụng để thoát khỏi các vòng lặp như `for`, `while`, `do-while` hoặc các cấu tr...
Meta Keywords: break, lặp, lệnh, trong, vòng
-->

# C++: Lệnh "break" trong C++

## Tóm tắt
Lệnh "break" trong C++ được sử dụng để thoát khỏi các vòng lặp như `for`, `while`, `do-while` hoặc các cấu trúc điều kiện `switch`. Nó giúp kiểm soát luồng thực thi của chương trình một cách hiệu quả.

## Tài liệu
Lệnh "break" trong C++ có chức năng dừng ngay lập tức vòng lặp hiện tại hoặc thoát khỏi cấu trúc `switch`. Khi lệnh "break" được thực thi, chương trình sẽ tiếp tục thực thi từ câu lệnh ngay sau vòng lặp hoặc `switch`.

### Cú pháp
```cpp
break;
```

### Mục đích
- **Thoát khỏi vòng lặp:** Khi điều kiện của vòng lặp không còn thỏa mãn, hoặc khi một điều kiện nào đó được xác định, lệnh "break" cho phép bạn kết thúc vòng lặp sớm.
- **Kết thúc cấu trúc `switch`:** Trong một cấu trúc `switch`, lệnh "break" ngăn không cho chương trình tiếp tục thực thi các nhánh sau.

### Cách sử dụng
Lệnh "break" thường được sử dụng trong các vòng lặp lặp đi lặp lại hoặc trong các cấu trúc điều kiện `switch`. Dưới đây là một số ví dụ minh họa.

## Ví dụ
### Ví dụ 1: Sử dụng trong vòng lặp `for`
```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            break; // Thoát khỏi vòng lặp khi i = 5
        }
        cout << i << " ";
    }
    return 0;
}
```
**Kết quả:** `0 1 2 3 4 `

### Ví dụ 2: Sử dụng trong cấu trúc `switch`
```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 3;
    switch (day) {
        case 1:
            cout << "Thứ Hai";
            break;
        case 2:
            cout << "Thứ Ba";
            break;
        case 3:
            cout << "Thứ Tư";
            break; // Kết thúc nhánh này
        default:
            cout << "Ngày không hợp lệ";
    }
    return 0;
}
```
**Kết quả:** `Thứ Tư`

## Giải thích
### Những cạm bẫy thường gặp
- **Lạm dụng lệnh "break":** Sử dụng quá nhiều lệnh "break" có thể làm cho mã nguồn trở nên khó hiểu và khó bảo trì. Nên cân nhắc tránh sử dụng lệnh này trong các vòng lặp lồng nhau nếu không thực sự cần thiết.
- **Lỗi khi không sử dụng "break" trong `switch`:** Nếu không sử dụng lệnh "break" sau mỗi nhánh trong `switch`, chương trình sẽ tiếp tục thực thi các nhánh tiếp theo, điều này có thể dẫn đến kết quả không mong muốn.

### Ghi chú bổ sung
- Lệnh "break" chỉ có hiệu lực trong vòng lặp hoặc cấu trúc `switch` mà nó được gọi.
- Trong các vòng lặp lồng nhau, "break" chỉ thoát ra khỏi vòng lặp gần nhất.

## Tóm tắt một dòng
Lệnh "break" trong C++ cho phép thoát khỏi vòng lặp hoặc cấu trúc `switch` ngay lập tức, giúp kiểm soát luồng thực thi của chương trình.