<!--
Meta Description: # C++ 中的 typename：型別指示符的詳細介紹 ## 概述 `typename` 是 C++ 中的一個關鍵字，用於指示一個名稱代表型別，特別是在模板編程中，它可以用來提升代碼的可讀性和正確性。 ## 文檔 `typename` 的主要用途在於明確指定一個模板參數是型別而非其他，例如變數或函...
Meta Keywords: typename, nested_type, cpp, template, void
-->

# C++ 中的 typename：型別指示符的詳細介紹

## 概述
`typename` 是 C++ 中的一個關鍵字，用於指示一個名稱代表型別，特別是在模板編程中，它可以用來提升代碼的可讀性和正確性。

## 文檔
`typename` 的主要用途在於明確指定一個模板參數是型別而非其他，例如變數或函數。這在涉及模板時特別重要，因為編譯器需要能夠正確解析出型別。`typename` 可以用在模板定義中，也可以用於指定嵌套型別。

### 用法
1. **模板型別參數**：
   ```cpp
   template<typename T>
   void func(T arg) {
       // 具體操作
   }
   ```

2. **嵌套型別**：
   ```cpp
   template<typename T>
   void func() {
       typename T::nested_type var; // 指示 nested_type 是型別
   }
   ```

## 範例
以下是 `typename` 的基本使用範例：

### 範例 1：模板函數
```cpp
#include <iostream>

template<typename T>
void printType(T arg) {
    std::cout << "Type: " << typeid(arg).name() << std::endl;
}

int main() {
    printType(5);         // 輸出整數型別
    printType(3.14);      // 輸出浮點型別
    return 0;
}
```

### 範例 2：嵌套型別
```cpp
#include <iostream>
#include <vector>

template<typename T>
class Wrapper {
public:
    using nested_type = std::vector<T>;

    void addElement(const T& element) {
        typename nested_type::iterator it; // 指示 it 是型別
        elements.push_back(element);
    }

private:
    nested_type elements;
};

int main() {
    Wrapper<int> intWrapper;
    intWrapper.addElement(10);
    return 0;
}
```

## 解釋
使用 `typename` 時，常見的陷阱包括：
- 忘記在模板中使用 `typename` 來指示嵌套型別，這將導致編譯錯誤。
- 將 `typename` 與 `class` 混淆，雖然在模板參數中可以互換使用，但在某些上下文中，選擇不當會導致混淆。

## 一句總結
`typename` 是 C++ 中的一個關鍵字，用於明確指定模板中的型別，提升代碼的可讀性與正確性。