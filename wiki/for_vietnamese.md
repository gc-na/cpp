<!--
Meta Description: # C++: Câu Lệnh "for" - Cách Sử Dụng và Ví Dụ Cụ Thể ## Tóm tắt Câu lệnh "for" trong C++ là một công cụ mạnh mẽ dùng để lặp qua các khối mã một số lần...
Meta Keywords: lặp, điều, một, các, int
-->

# C++: Câu Lệnh "for" - Cách Sử Dụng và Ví Dụ Cụ Thể

## Tóm tắt
Câu lệnh "for" trong C++ là một công cụ mạnh mẽ dùng để lặp qua các khối mã một số lần xác định, giúp lập trình viên thực hiện các thao tác lặp lại một cách hiệu quả và dễ dàng.

## Tài liệu
Câu lệnh "for" trong C++ được sử dụng để lặp qua một khối mã với một điều kiện nhất định. Cấu trúc cơ bản của câu lệnh "for" như sau:

```cpp
for (khởi_tạo; điều_kiện; cập_nhật) {
    // Khối mã sẽ được thực thi nếu điều kiện là đúng
}
```

- **khởi_tạo**: Khởi tạo biến điều khiển vòng lặp (thường là một biến số nguyên).
- **điều_kiện**: Điều kiện lặp lại; vòng lặp sẽ tiếp tục cho đến khi điều kiện này trở thành sai.
- **cập_nhật**: Biểu thức được thực thi sau mỗi lần lặp, thường dùng để thay đổi giá trị của biến điều khiển.

### Mục đích
Câu lệnh "for" cho phép lập trình viên lặp lại các thao tác một cách có tổ chức, đặc biệt hữu ích trong việc duyệt qua các mảng hoặc thực hiện các phép toán lặp lại.

### Cách sử dụng
Ví dụ cơ bản về cách sử dụng câu lệnh "for":

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 5; i++) {
        cout << "Giá trị của i: " << i << endl;
    }
    return 0;
}
```

Trong ví dụ trên, biến `i` được khởi tạo là 0 và vòng lặp sẽ tiếp tục cho đến khi `i` nhỏ hơn 5. Sau mỗi lần lặp, `i` sẽ được tăng lên 1.

## Ví dụ
### Ví dụ 1: Lặp qua mảng

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int n = sizeof(arr) / sizeof(arr[0]);

    for (int i = 0; i < n; i++) {
        cout << "Giá trị của arr[" << i << "] là: " << arr[i] << endl;
    }
    return 0;
}
```

### Ví dụ 2: Tổng các số từ 1 đến 10

```cpp
#include <iostream>
using namespace std;

int main() {
    int sum = 0;
    for (int i = 1; i <= 10; i++) {
        sum += i;
    }
    cout << "Tổng các số từ 1 đến 10 là: " << sum << endl;
    return 0;
}
```

## Giải thích
Khi sử dụng câu lệnh "for", có một số điểm cần lưu ý:

1. **Chú ý đến điều kiện**: Nếu điều kiện không đúng, vòng lặp sẽ không bao giờ thực hiện, hoặc nếu điều kiện luôn đúng, vòng lặp có thể chạy vô hạn.
2. **Thay đổi biến điều khiển**: Đảm bảo rằng biến điều khiển được cập nhật đúng cách để tránh vòng lặp vô hạn.
3. **Sử dụng đúng loại dữ liệu**: Đối với các vòng lặp trên mảng, đảm bảo rằng chỉ số không vượt quá kích thước của mảng, điều này có thể dẫn đến truy cập ngoài phạm vi và gây ra lỗi.

## Tóm tắt một dòng
Câu lệnh "for" trong C++ là một công cụ lặp mạnh mẽ, cho phép thực hiện các thao tác lặp lại một cách hiệu quả và dễ dàng.