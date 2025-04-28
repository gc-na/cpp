<!--
Meta Description: # Từ Khóa "friend" trong C++: Đặc Điểm và Cách Sử Dụng ## Tóm tắt Từ khóa `friend` trong C++ cho phép một hàm hoặc lớp truy cập vào các thành viên riê...
Meta Keywords: lớp, box, friend, của, một
-->

# Từ Khóa "friend" trong C++: Đặc Điểm và Cách Sử Dụng

## Tóm tắt
Từ khóa `friend` trong C++ cho phép một hàm hoặc lớp truy cập vào các thành viên riêng tư và bảo vệ của lớp khác, giúp tăng cường khả năng tương tác giữa các lớp mà không làm giảm tính bảo mật của dữ liệu.

## Tài liệu

### Mục đích
Từ khóa `friend` được sử dụng để khai báo một hàm hoặc một lớp là bạn của lớp khác. Điều này cho phép hàm hoặc lớp bạn này có quyền truy cập tới các thành viên (bao gồm cả biến và phương thức) riêng tư hoặc bảo vệ của lớp đó.

### Cách sử dụng
- **Khai báo hàm friend:** Bạn có thể khai báo một hàm bên ngoài lớp như là một hàm bạn.
- **Khai báo lớp friend:** Một lớp có thể được khai báo là bạn của một lớp khác, từ đó cho phép tất cả các phương thức của lớp bạn truy cập vào các thành viên riêng tư của lớp chính.

### Chi tiết
Khi bạn sử dụng từ khóa `friend`, bạn nên lưu ý rằng:
- `friend` không hình thành quan hệ kế thừa.
- Quyền truy cập chỉ giới hạn trong các thành viên của lớp mà đã được khai báo là bạn, không phải toàn bộ lớp.
- Từ khóa `friend` chỉ có hiệu lực trong ngữ cảnh của lớp chứa nó.

## Ví dụ

### Ví dụ 1: Hàm friend
```cpp
#include <iostream>
using namespace std;

class Box {
private:
    int width;
public:
    Box(int w) : width(w) {}
    friend void printWidth(Box box);
};

void printWidth(Box box) {
    cout << "Width of box: " << box.width << endl;
}

int main() {
    Box box(10);
    printWidth(box);
    return 0;
}
```

### Ví dụ 2: Lớp friend
```cpp
#include <iostream>
using namespace std;

class Box {
private:
    int width;
public:
    Box(int w) : width(w) {}
    friend class BoxPrinter; // Khai báo BoxPrinter là lớp friend
};

class BoxPrinter {
public:
    void printWidth(Box box) {
        cout << "Width of box: " << box.width << endl;
    }
};

int main() {
    Box box(10);
    BoxPrinter printer;
    printer.printWidth(box);
    return 0;
}
```

## Giải thích
Một số điểm cần chú ý khi sử dụng từ khóa `friend`:
- **Độ phức tạp:** Sử dụng quá nhiều `friend` có thể làm cho mã trở nên khó hiểu và khó bảo trì. Nên sử dụng nó một cách thận trọng.
- **Bảo mật:** Mặc dù `friend` cho phép truy cập vào các thành viên riêng tư, nhưng việc lạm dụng nó có thể dẫn đến việc vi phạm nguyên tắc ẩn giấu dữ liệu.
- **Tính kế thừa:** Lớp con không tự động trở thành bạn của lớp cha, ngay cả khi lớp cha là bạn của một lớp khác.

## Tóm tắt một dòng
Từ khóa `friend` trong C++ cho phép hàm hoặc lớp truy cập vào các thành viên riêng tư của lớp khác, tạo điều kiện thuận lợi cho việc tương tác giữa các lớp.