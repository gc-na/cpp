<!--
Meta Description: # Toán Tử Trong C++ ## Tóm Tắt Toán tử trong C++ là các ký hiệu đặc biệt được sử dụng để thực hiện các phép toán trên biến và giá trị. Chúng cho phép ...
Meta Keywords: toán, các, phép, gán, giá
-->

# Toán Tử Trong C++

## Tóm Tắt
Toán tử trong C++ là các ký hiệu đặc biệt được sử dụng để thực hiện các phép toán trên biến và giá trị. Chúng cho phép lập trình viên thực hiện các thao tác như toán học, so sánh và gán giá trị.

## Tài Liệu
Trong C++, toán tử có thể được chia thành nhiều loại khác nhau, bao gồm:

1. **Toán tử số học**: Dùng để thực hiện các phép toán như cộng, trừ, nhân, chia.
   - `+` (cộng)
   - `-` (trừ)
   - `*` (nhân)
   - `/` (chia)
   - `%` (chia lấy dư)

2. **Toán tử so sánh**: Dùng để so sánh các giá trị và trả về giá trị boolean.
   - `==` (bằng)
   - `!=` (không bằng)
   - `<` (nhỏ hơn)
   - `>` (lớn hơn)
   - `<=` (nhỏ hơn hoặc bằng)
   - `>=` (lớn hơn hoặc bằng)

3. **Toán tử logic**: Dùng để thực hiện các phép toán logic.
   - `&&` (và)
   - `||` (hoặc)
   - `!` (không)

4. **Toán tử gán**: Dùng để gán giá trị cho biến.
   - `=` (gán)
   - `+=`, `-=`, `*=`, `/=`, `%=` (gán kết hợp)

5. **Toán tử tăng/giảm**: Dùng để tăng hoặc giảm giá trị của biến.
   - `++` (tăng)
   - `--` (giảm)

Mỗi loại toán tử có cách sử dụng riêng và có thể kết hợp với nhau để thực hiện các phép toán phức tạp hơn.

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng các toán tử trong C++:

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 5;

    // Toán tử số học
    cout << "Tổng: " << (a + b) << endl; // 15
    cout << "Hiệu: " << (a - b) << endl; // 5

    // Toán tử so sánh
    cout << "a bằng b? " << (a == b) << endl; // 0 (false)

    // Toán tử logic
    if (a > b && b > 0) {
        cout << "Điều kiện đúng" << endl; // In ra
    }

    // Toán tử gán
    a += b; // a = a + b
    cout << "Giá trị của a sau khi gán: " << a << endl; // 15

    return 0;
}
```

## Giải Thích
Khi sử dụng toán tử trong C++, lập trình viên cần chú ý đến thứ tự ưu tiên và độ kết hợp của các toán tử. Một số lỗi phổ biến có thể xảy ra:

- **Lỗi thứ tự ưu tiên**: Nếu không hiểu rõ thứ tự ưu tiên của các toán tử, kết quả của phép toán có thể không như mong đợi. Ví dụ, phép nhân (`*`) có độ ưu tiên cao hơn phép cộng (`+`).
  
- **Lỗi kiểu dữ liệu**: Các toán tử có thể không hoạt động đúng nếu kiểu dữ liệu không tương thích. Ví dụ, cố gắng cộng một số nguyên với một chuỗi sẽ gây ra lỗi biên dịch.

- **Toán tử gán không chính xác**: Đôi khi, lập trình viên có thể nhầm lẫn giữa toán tử gán `=` và toán tử so sánh `==`, dẫn đến các lỗi logic trong chương trình.

## Tóm Tắt Một Dòng
Toán tử trong C++ là các ký hiệu đặc biệt cho phép thực hiện các phép toán trên biến và giá trị, bao gồm toán học, so sánh và gán.