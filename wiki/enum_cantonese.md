<!--
Meta Description: # C++ 中的枚舉 (enum)：用法與示例 ## 簡介 在 C++ 編程語言中，枚舉（enum）是一種用於定義一組整數常量的數據類型。它可以提高代碼的可讀性和可維護性，並且使代碼更加自描述。 ## 文檔 ### 目的 枚舉（enum）主要用於創建一組具名的整數常量，便於在代碼中使用和理解。這使得...
Meta Keywords: enum, cpp, green, class, std
-->

# C++ 中的枚舉 (enum)：用法與示例

## 簡介
在 C++ 編程語言中，枚舉（enum）是一種用於定義一組整數常量的數據類型。它可以提高代碼的可讀性和可維護性，並且使代碼更加自描述。

## 文檔
### 目的
枚舉（enum）主要用於創建一組具名的整數常量，便於在代碼中使用和理解。這使得代碼更加易於維護及閱讀。

### 用法
在 C++ 中，枚舉的定義使用 `enum` 關鍵字。其基本語法如下：

```cpp
enum EnumName {
    Constant1,
    Constant2,
    Constant3,
    // ... 
};
```

#### 詳細說明
- **EnumName**：這是枚舉的名稱，可以在代碼中用來引用這組常量。
- **Constant1, Constant2, Constant3**：這些是枚舉的成員，默認的整數值從 0 開始，依次遞增。如果需要，可以為某些成員指定具體的整數值。

例如：

```cpp
enum Color {
    Red,    // 默認為 0
    Green,  // 默認為 1
    Blue    // 默認為 2
};
```

此外，C++11 引入了「強類型枚舉」，使用 `enum class` 定義的枚舉類型更為安全，避免了名稱沖突：

```cpp
enum class Fruit {
    Apple,
    Banana,
    Orange
};
```

### 使用示例
以下是 C++ 枚舉的基本使用示例：

```cpp
#include <iostream>

enum Day {
    Sunday,
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday
};

int main() {
    Day today = Wednesday;

    if (today == Wednesday) {
        std::cout << "今天是星期三！" << std::endl;
    }

    return 0;
}
```

強類型枚舉的示例：

```cpp
#include <iostream>

enum class TrafficLight {
    Red,
    Yellow,
    Green
};

int main() {
    TrafficLight light = TrafficLight::Green;

    if (light == TrafficLight::Green) {
        std::cout << "可以通行！" << std::endl;
    }

    return 0;
}
```

## 解釋
### 常見陷阱與注意事項
1. **名稱沖突**：使用普通枚舉時，常量名稱會引入到當前命名空間，可能會與其他變量產生衝突。使用 `enum class` 可以有效避免此問題。
   
2. **自定義整數值**：可以為枚舉的成員指定整數值，但如果不小心，可能會導致意外的行為。例如：

   ```cpp
   enum ErrorCode {
       Success = 0,
       NotFound = 404,
       ServerError = 500
   };
   ```

3. **隱式轉換**：普通枚舉可以隱式轉換為整數類型，而強類型枚舉則不可，這可以提高類型安全性。

## 單行總結
C++ 中的枚舉（enum）是一種用於定義一組具名整數常量的數據類型，增強了代碼的可讀性和可維護性。