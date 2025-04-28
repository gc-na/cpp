<!--
Meta Description: # Lệnh "continue" trong C++ ## Tóm tắt Lệnh `continue` trong C++ được sử dụng trong các vòng lặp để bỏ qua phần còn lại của vòng lặp hiện tại và tiếp ...
Meta Keywords: lặp, vòng, continue, trong, dụng
-->

# Lệnh "continue" trong C++

## Tóm tắt
Lệnh `continue` trong C++ được sử dụng trong các vòng lặp để bỏ qua phần còn lại của vòng lặp hiện tại và tiếp tục với vòng lặp tiếp theo. Điều này cho phép lập trình viên kiểm soát luồng của vòng lặp một cách linh hoạt.

## Tài liệu
Lệnh `continue` là một trong những câu lệnh điều khiển trong C++. Nó chủ yếu được sử dụng trong các cấu trúc lặp như `for`, `while` và `do-while`. Khi gặp lệnh `continue`, chương trình sẽ bỏ qua bất kỳ câu lệnh nào còn lại trong vòng lặp hiện tại và quay lại điều kiện để kiểm tra xem vòng lặp có nên tiếp tục hay không.

### Cú pháp
```cpp
continue;
```

### Mục đích
- Bỏ qua các câu lệnh còn lại trong vòng lặp hiện tại.
- Tiến đến vòng lặp tiếp theo ngay lập tức.

### Sử dụng
- Có thể được sử dụng trong vòng lặp `for`, `while` và `do-while`.
- Thích hợp khi bạn muốn bỏ qua các điều kiện hoặc xử lý không cần thiết trong một vòng lặp.

## Ví dụ
### Ví dụ 1: Sử dụng `continue` trong vòng lặp `for`
```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 10; i++) {
        if (i % 2 == 0) {
            continue; // Bỏ qua số chẵn
        }
        cout << i << " "; // In ra số lẻ
    }
    return 0;
}
```
**Kết quả:** `1 3 5 7 9`

### Ví dụ 2: Sử dụng `continue` trong vòng lặp `while`
```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    while (i <= 10) {
        i++;
        if (i % 2 == 0) {
            continue; // Bỏ qua số chẵn
        }
        cout << i << " "; // In ra số lẻ
    }
    return 0;
}
```
**Kết quả:** `3 5 7 9 11`

## Giải thích
Khi sử dụng lệnh `continue`, cần lưu ý một số điểm quan trọng:
- `continue` chỉ ảnh hưởng đến vòng lặp ngay lập tức nơi nó được sử dụng. Nếu có nhiều vòng lặp lồng nhau, chỉ vòng lặp gần nhất sẽ bị ảnh hưởng.
- Việc sử dụng `continue` quá nhiều có thể làm cho mã trở nên khó đọc và khó bảo trì. Hãy sử dụng nó một cách hợp lý để đảm bảo mã vẫn dễ hiểu.
- Đảm bảo rằng điều kiện để thoát khỏi vòng lặp vẫn được thực hiện, tránh tình trạng vòng lặp vô hạn.

## Tóm tắt một câu
Lệnh `continue` trong C++ cho phép lập trình viên bỏ qua phần còn lại của vòng lặp hiện tại và tiếp tục với vòng lặp tiếp theo, giúp kiểm soát luồng thực thi một cách linh hoạt.