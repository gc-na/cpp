<!--
Meta Description: # C++ 模板 (Template) 使用指南 ## 摘要 C++ 模板是一種強大的特性，允許開發者撰寫能夠運行在多種類型上的通用程式碼。這使得代碼重用性大幅提高，並且簡化了類和函數的設計。 ## 文檔 模板是 C++ 中的一種編程技術，提供了一種在編譯時生成類或函數的機制，而不需要為每一種數據類...
Meta Keywords: value, template, return, box, cpp
-->

# C++ 模板 (Template) 使用指南

## 摘要
C++ 模板是一種強大的特性，允許開發者撰寫能夠運行在多種類型上的通用程式碼。這使得代碼重用性大幅提高，並且簡化了類和函數的設計。

## 文檔
模板是 C++ 中的一種編程技術，提供了一種在編譯時生成類或函數的機制，而不需要為每一種數據類型都寫相應的代碼。C++ 模板主要有兩種形式：函數模板和類模板。

### 目的
使用模板的主要目的是創建通用性強的函數和類，以減少重複代碼的需求，提高開發效率和維護性。

### 使用方法
1. **函數模板**：通過關鍵字 `template` 定義，能夠接受任意數據類型。
   ```cpp
   template <typename T>
   T add(T a, T b) {
       return a + b;
   }
   ```

2. **類模板**：同樣使用 `template` 定義，能夠創建可處理多種數據類型的類。
   ```cpp
   template <typename T>
   class Box {
   public:
       Box(T value) : value(value) {}
       T getValue() {
           return value;
       }
   private:
       T value;
   };
   ```

## 範例
### 函數模板範例
```cpp
#include <iostream>
using namespace std;

template <typename T>
T add(T a, T b) {
    return a + b;
}

int main() {
    cout << "整數相加: " << add(5, 3) << endl; // 輸出: 8
    cout << "浮點數相加: " << add(5.5, 3.3) << endl; // 輸出: 8.8
    return 0;
}
```

### 類模板範例
```cpp
#include <iostream>
using namespace std;

template <typename T>
class Box {
public:
    Box(T value) : value(value) {}
    T getValue() {
        return value;
    }
private:
    T value;
};

int main() {
    Box<int> intBox(123);
    Box<string> strBox("Hello");

    cout << "整數盒子中的值: " << intBox.getValue() << endl; // 輸出: 123
    cout << "字串盒子中的值: " << strBox.getValue() << endl; // 輸出: Hello
    return 0;
}
```

## 解釋
使用模板時，開發者需要注意以下幾點：
- **類型推導**：在調用函數模板時，編譯器會自動推導參數類型，但在某些情況下，可能需要明確指定類型。
- **模板特化**：可以為特定的數據類型提供特別的實現，這稱為模板特化。
- **編譯錯誤信息**：模板的編譯錯誤信息有時會比較模糊，這可能會讓調試變得困難。

## 一句總結
C++ 模板是一種強大的工具，可用於編寫通用函數和類，以提高代碼的重用性和靈活性。