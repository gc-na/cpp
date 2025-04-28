<!--
Meta Description: # Tìm hiểu về Toán Tử XOR trong C++ ## Tóm tắt Toán tử XOR (Exclusive OR) trong C++ là một toán tử bitwise, được sử dụng để thực hiện phép toán logic ...
Meta Keywords: toán, xor, một, trong, hai
-->

# Tìm hiểu về Toán Tử XOR trong C++

## Tóm tắt
Toán tử XOR (Exclusive OR) trong C++ là một toán tử bitwise, được sử dụng để thực hiện phép toán logic trên các bit. Nó trả về giá trị đúng (1) nếu chỉ một trong hai toán hạng là đúng (1), và sai (0) nếu cả hai đều đúng hoặc cả hai đều sai.

## Tài liệu
Toán tử XOR trong C++ được ký hiệu bằng `^`. Nó làm việc trên các kiểu số nguyên, bao gồm `int`, `long`, và `char`. Khi áp dụng toán tử này, mỗi bit tương ứng giữa hai toán hạng được so sánh:

- Nếu cả hai bit là 0, kết quả là 0.
- Nếu một bit là 0 và bit còn lại là 1, kết quả là 1.
- Nếu cả hai bit là 1, kết quả là 0.

### Cú pháp
```cpp
int result = a ^ b;
```

### Ví dụ sử dụng
```cpp
#include <iostream>

int main() {
    int a = 5;  // Nhị phân: 0101
    int b = 3;  // Nhị phân: 0011
    int result = a ^ b; // Kết quả: 0110 (6)
    
    std::cout << "Kết quả của a ^ b là: " << result << std::endl; // In ra 6
    return 0;
}
```

## Giải thích
Khi sử dụng toán tử XOR, cần lưu ý một số điểm sau:

1. **Tính chất giao hoán**: A ^ B = B ^ A. Thứ tự của các toán hạng không ảnh hưởng đến kết quả.
2. **Tính chất kết hợp**: (A ^ B) ^ C = A ^ (B ^ C). Bạn có thể nhóm các phép toán một cách linh hoạt.
3. **XOR với 0**: Bất kỳ giá trị nào XOR với 0 đều giữ nguyên giá trị đó. Ví dụ, `a ^ 0 = a`.
4. **XOR với chính nó**: Bất kỳ giá trị nào XOR với chính nó sẽ cho ra 0. Ví dụ, `a ^ a = 0`.

Một số cạm bẫy có thể gặp khi sử dụng toán tử này bao gồm:

- Nhầm lẫn giữa XOR và OR. Toán tử OR (`|`) sẽ trả về 1 nếu ít nhất một trong hai bit là 1, trong khi XOR chỉ trả về 1 khi chỉ một trong hai bit là 1.
- Đối với các kiểu dữ liệu không phải số nguyên, XOR có thể không hoạt động như mong đợi.

## Tóm tắt một dòng
Toán tử XOR trong C++ là một phép toán bitwise, trả về giá trị đúng nếu một trong hai toán hạng khác nhau, và sai nếu chúng giống nhau.