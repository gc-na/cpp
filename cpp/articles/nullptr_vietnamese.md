<!--
Meta Description: # Tìm Hiểu Về nullptr Trong C++ ## Tóm Tắt `nullptr` là một hằng số đại diện cho một con trỏ rỗng trong C++, được giới thiệu từ phiên bản C++11. Nó gi...
Meta Keywords: trỏ, con, nullptr, dụng, trong
-->

# Tìm Hiểu Về nullptr Trong C++

## Tóm Tắt
`nullptr` là một hằng số đại diện cho một con trỏ rỗng trong C++, được giới thiệu từ phiên bản C++11. Nó giúp cải thiện tính rõ ràng và an toàn hơn so với việc sử dụng `NULL` hay `0` để đại diện cho con trỏ không trỏ đến bất kỳ đối tượng nào.

## Tài Liệu
### Mục Đích
`nullptr` được sử dụng để biểu thị rằng một con trỏ không trỏ đến bất kỳ địa chỉ bộ nhớ nào. Điều này rất hữu ích trong việc phân biệt giữa con trỏ và các kiểu số nguyên, tránh nhầm lẫn và lỗi trong mã.

### Cách Sử Dụng
- **Khai báo con trỏ rỗng:** Bạn có thể khởi tạo một con trỏ với giá trị `nullptr` thay vì `NULL` hoặc `0`.
- **Kiểm tra con trỏ:** Sử dụng `nullptr` trong các điều kiện để kiểm tra xem một con trỏ có rỗng hay không.
- **Gọi hàm:** `nullptr` có thể được sử dụng để gọi hàm mà có nhiều phiên bản quá tải mà các tham số đầu vào có thể là con trỏ.

### Chi Tiết
- `nullptr` là một kiểu dữ liệu riêng biệt, có loại là `std::nullptr_t`, giúp cho việc truyền nó vào các hàm hoặc so sánh với các kiểu con trỏ trở nên thuận tiện hơn.
- Việc sử dụng `nullptr` giúp compiler có thể phát hiện lỗi và cảnh báo khi bạn cố gắng sử dụng các con trỏ không hợp lệ.

## Ví Dụ
### Ví Dụ 1: Khởi Tạo Con Trỏ
```cpp
int* ptr = nullptr; // Khởi tạo con trỏ ptr với giá trị rỗng
```

### Ví Dụ 2: Kiểm Tra Con Trỏ
```cpp
if (ptr == nullptr) {
    std::cout << "Con trỏ ptr là rỗng." << std::endl;
}
```

### Ví Dụ 3: Gọi Hàm Với Nhiều Phiên Bản Quá Tải
```cpp
void func(int* p) {
    std::cout << "Đây là con trỏ int." << std::endl;
}

void func(char* p) {
    std::cout << "Đây là con trỏ char." << std::endl;
}

func(nullptr); // Gọi phiên bản hàm nào cũng được
```

## Giải Thích
Một số vấn đề thường gặp khi sử dụng `nullptr` bao gồm:
- **Nhầm lẫn với các kiểu số nguyên:** Trước khi có `nullptr`, việc sử dụng `0` hoặc `NULL` có thể gây nhầm lẫn giữa con trỏ và kiểu số nguyên, điều này có thể dẫn đến lỗi thời gian biên dịch hoặc thời gian chạy.
- **Hỗ trợ trong các phiên bản cũ hơn:** Nếu bạn làm việc với các mã nguồn cũ, bạn có thể thấy việc sử dụng `NULL` vẫn phổ biến. Tuy nhiên, `nullptr` là lựa chọn tốt hơn trong C++ hiện đại.
  
## Tóm Tắt Một Dòng
`nullptr` là một hằng số an toàn và rõ ràng để biểu thị con trỏ rỗng trong C++, giúp tránh nhầm lẫn và lỗi trong mã.