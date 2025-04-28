<!--
Meta Description: # Vòng Lặp "while" Trong C++: Cách Sử Dụng và Ví Dụ ## Tóm Tắt Vòng lặp "while" trong C++ là một cấu trúc điều khiển cho phép thực hiện một khối mã lặ...
Meta Keywords: lặp, vòng, điều, một, while
-->

# Vòng Lặp "while" Trong C++: Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Vòng lặp "while" trong C++ là một cấu trúc điều khiển cho phép thực hiện một khối mã lặp đi lặp lại miễn là điều kiện xác định là đúng (true).

## Tài Liệu
### Mục Đích
Vòng lặp "while" được sử dụng để lặp qua một khối mã cho đến khi điều kiện kiểm tra trở thành sai (false). Điều này hữu ích trong nhiều tình huống như đọc dữ liệu từ người dùng cho đến khi nhận được giá trị hợp lệ hoặc thực hiện các phép toán cho đến khi đạt được một mục tiêu nhất định.

### Cú Pháp
Cú pháp cơ bản của vòng lặp "while" như sau:
```cpp
while (điều_kiện) {
    // Khối mã sẽ được thực thi khi điều kiện đúng
}
```

### Chi Tiết
- **Điều Kiện**: Là một biểu thức boolean. Nếu điều kiện này trả về true, khối mã bên trong vòng lặp sẽ được thực thi.
- **Khối Mã**: Là các câu lệnh sẽ được thực thi. Nếu không có câu lệnh nào, vòng lặp có thể dẫn đến một vòng lặp vô hạn.

## Ví Dụ
### Ví dụ Cơ Bản
Dưới đây là một ví dụ đơn giản về cách sử dụng vòng lặp "while" để in ra các số từ 1 đến 5:
```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    while (i <= 5) {
        cout << i << endl;
        i++;
    }
    return 0;
}
```

### Ví dụ Với Điều Kiện Phức Tạp
Trong ví dụ này, vòng lặp sẽ tiếp tục cho đến khi người dùng nhập giá trị âm:
```cpp
#include <iostream>
using namespace std;

int main() {
    int number;
    cout << "Nhập một số dương (nhập số âm để kết thúc): ";
    cin >> number;

    while (number >= 0) {
        cout << "Bạn đã nhập: " << number << endl;
        cout << "Nhập một số dương (nhập số âm để kết thúc): ";
        cin >> number;
    }

    return 0;
}
```

## Giải Thích
### Những Điều Cần Lưu Ý
1. **Vòng Lặp Vô Hạn**: Nếu điều kiện trong vòng lặp "while" luôn đúng, chương trình sẽ không bao giờ thoát khỏi vòng lặp, dẫn đến một vòng lặp vô hạn. Cần đảm bảo rằng điều kiện sẽ trở thành sai tại một thời điểm nào đó.
2. **Khối Mã Trống**: Nếu khối mã bên trong vòng lặp "while" trống, điều này có thể gây ra nhầm lẫn. Nên sử dụng từ khóa `break` hoặc `continue` nếu cần thiết để điều khiển luồng của vòng lặp.
3. **Kiểm Tra Điều Kiện Trước**: Vòng lặp "while" kiểm tra điều kiện trước khi thực hiện khối mã, nếu điều kiện sai ngay từ đầu, khối mã sẽ không bao giờ được thực thi.

## Tóm Tắt Một Dòng
Vòng lặp "while" trong C++ cho phép thực hiện một khối mã lặp đi lặp lại miễn là điều kiện được chỉ định vẫn đúng.