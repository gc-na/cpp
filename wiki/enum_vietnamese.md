<!--
Meta Description: # Enum trong C++: Khái Niệm và Cách Sử Dụng ## Tóm tắt `enum` (liệt kê) trong C++ là một kiểu dữ liệu cho phép bạn định nghĩa một tập hợp các giá trị ...
Meta Keywords: enum, các, dụng, thể, một
-->

# Enum trong C++: Khái Niệm và Cách Sử Dụng

## Tóm tắt
`enum` (liệt kê) trong C++ là một kiểu dữ liệu cho phép bạn định nghĩa một tập hợp các giá trị hằng số có tên. Điều này giúp mã nguồn trở nên dễ đọc và dễ bảo trì hơn, đồng thời tăng tính an toàn cho biến khi lập trình.

## Tài liệu
### Mục đích
`enum` được sử dụng để định nghĩa các hằng số có liên quan, giúp cải thiện khả năng đọc hiểu của mã. Thay vì sử dụng các số nguyên hoặc chuỗi không có ý nghĩa, bạn có thể sử dụng các tên rõ ràng để đại diện cho các giá trị cụ thể.

### Cú pháp
```cpp
enum EnumName {
    Value1,
    Value2,
    Value3,
    // ...
};
```

### Sử dụng
Để sử dụng `enum`, trước tiên bạn định nghĩa một kiểu enum và sau đó có thể khai báo biến của kiểu đó. Ví dụ:
```cpp
enum Color {
    RED,
    GREEN,
    BLUE
};

Color myColor = RED;
```

### Chi tiết
- Mặc định, các giá trị trong `enum` bắt đầu từ 0 và tăng dần. Bạn có thể chỉ định giá trị cụ thể cho các hằng số nếu cần:
```cpp
enum Status {
    SUCCESS = 0,
    ERROR = 1,
    UNKNOWN = 2
};
```
- C++11 đã giới thiệu `enum class`, giúp tăng cường tính an toàn kiểu dữ liệu và tránh xung đột tên giữa các enum khác nhau:
```cpp
enum class Direction {
    NORTH,
    SOUTH,
    EAST,
    WEST
};

// Cách sử dụng
Direction dir = Direction::NORTH;
```

## Ví dụ
### Ví dụ cơ bản về enum
```cpp
#include <iostream>

enum Day {
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY,
    SUNDAY
};

int main() {
    Day today = WEDNESDAY;
    if (today == WEDNESDAY) {
        std::cout << "Hôm nay là thứ Tư!" << std::endl;
    }
    return 0;
}
```

### Ví dụ về enum class
```cpp
#include <iostream>

enum class Season {
    SPRING,
    SUMMER,
    FALL,
    WINTER
};

int main() {
    Season currentSeason = Season::SUMMER;
    if (currentSeason == Season::SUMMER) {
        std::cout << "Mùa hè đang đến!" << std::endl;
    }
    return 0;
}
```

## Giải thích
Khi sử dụng `enum`, có một số điểm cần lưu ý:
- Kiểu dữ liệu của `enum` là số nguyên, vì vậy bạn nên cẩn trọng khi so sánh các giá trị. Nếu không sử dụng `enum class`, có thể xảy ra xung đột tên giữa các `enum` khác nhau.
- `enum class` chỉ có thể được truy cập thông qua tên của enum đó (ví dụ: `Season::SUMMER`), giúp tránh tình trạng xung đột và cải thiện tính rõ ràng của mã.

## Tóm tắt một dòng
`enum` trong C++ là một cách hiệu quả để định nghĩa tập hợp các hằng số có tên, giúp mã nguồn dễ đọc và bảo trì hơn.