<!--
Meta Description: # C++ 中的 `static` 關鍵字 ## 簡介 `static` 是 C++ 中的一個關鍵字，用來定義靜態變數和靜態方法。它的使用範圍包括全域變數、類別成員和區域變數，能夠影響變數的生命週期和可見性。 ## 文檔 ### 目的 `static` 關鍵字的主要目的是控制變數的存儲方式和生命週期...
Meta Keywords: static, myclass, count, int, std
-->

# C++ 中的 `static` 關鍵字

## 簡介
`static` 是 C++ 中的一個關鍵字，用來定義靜態變數和靜態方法。它的使用範圍包括全域變數、類別成員和區域變數，能夠影響變數的生命週期和可見性。

## 文檔
### 目的
`static` 關鍵字的主要目的是控制變數的存儲方式和生命週期。當變數被聲明為 `static` 時，它的值會在整個程序的執行期間保持不變，並且不會隨著函數調用的結束而消失。

### 用法
1. **靜態區域變數**：在函數內部聲明為 `static` 的變數，會在函數的多次調用之間保持其值。
   ```cpp
   void function() {
       static int count = 0; // 初始化只執行一次
       count++;
       std::cout << count << std::endl;
   }
   ```
   
2. **靜態成員變數**：在類別中聲明為 `static` 的變數，屬於類別而不是類別的實例，所有實例共享同一個靜態變數。
   ```cpp
   class MyClass {
   public:
       static int staticVar;
   };

   int MyClass::staticVar = 0; // 定義靜態成員變數
   ```

3. **靜態成員函數**：靜態函數不能訪問非靜態成員，因為它不依賴於類的實例。
   ```cpp
   class MyClass {
   public:
       static void staticFunction() {
           std::cout << "Static function called!" << std::endl;
       }
   };
   ```

### 詳細說明
- **靜態區域變數**的生命週期持續到程序結束。它們的值在函數結束後不會被銷毀。
- **靜態成員變數**的生命週期同樣持久化於整個程序執行期間，並且可以在所有類的實例間共享。
- **靜態成員函數**能夠被類的實例或類本身調用，適合用於那些不需要物件狀態的操作。

## 示例
以下示範如何使用 `static`:
```cpp
#include <iostream>

class MyClass {
public:
    static int count; // 靜態成員變數
    MyClass() {
        count++; // 每次創建 MyClass 的實例時增加計數
    }
    static void displayCount() {
        std::cout << "Total instances: " << count << std::endl;
    }
};

int MyClass::count = 0; // 初始化靜態成員變數

int main() {
    MyClass obj1;
    MyClass obj2;
    MyClass::displayCount(); // 輸出: Total instances: 2
    return 0;
}
```

## 解釋
- **常見陷阱**：靜態區域變數的初始化只執行一次，這可能導致意想不到的行為。如果在多個函數中使用靜態變數，必須小心其狀態。
- **靜態成員的初始化**：靜態成員需在類外部進行定義和初始化。
- **不可以在靜態成員函數中使用非靜態成員**，因為靜態成員函數無法訪問實例上下文。

## 一句總結
`static` 關鍵字在 C++ 中用於定義靜態變數和靜態函數，以控制其生命週期和可見性。