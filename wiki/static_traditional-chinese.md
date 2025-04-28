<!--
Meta Description: # C++中的static關鍵字：使用與技巧 ## 概述 在C++中，`static`關鍵字是一個多用途的修飾符，用於控制變數和函數的生命週期及可見性。它可以用於全局變數、靜態變數及靜態成員函數，並在不同的上下文中具有不同的功能。 ## 文檔 ### 目的 `static`關鍵字的主要目的是管理變數...
Meta Keywords: static, std, int, counter, example
-->

# C++中的static關鍵字：使用與技巧

## 概述
在C++中，`static`關鍵字是一個多用途的修飾符，用於控制變數和函數的生命週期及可見性。它可以用於全局變數、靜態變數及靜態成員函數，並在不同的上下文中具有不同的功能。

## 文檔
### 目的
`static`關鍵字的主要目的是管理變數的存儲期和作用域。它允許變數在函數結束後仍然保持其值，並且限制變數的可見性，使其只能在定義它的文件或函數中使用。

### 使用
1. **靜態局部變數**：
   當在函數中宣告一個變數為`static`時，這個變數的生命週期會持續到程序結束，而不僅僅是函數調用期間。
   ```cpp
   void function() {
       static int count = 0; // 初始化只會執行一次
       count++;
       std::cout << count << std::endl;
   }
   ```

2. **靜態全局變數**：
   將全局變數標記為`static`會使其只能在定義它的文件中可見，防止命名衝突。
   ```cpp
   static int globalVar = 10; // 只能在此文件中使用
   ```

3. **靜態成員變數**：
   在類中，靜態成員變數屬於類別本身，而不是類的任何實例。它的值在所有對象之間共享。
   ```cpp
   class MyClass {
   public:
       static int objectCount;
       MyClass() { objectCount++; }
   };
   int MyClass::objectCount = 0; // 初始化靜態成員
   ```

4. **靜態成員函數**：
   靜態成員函數只能訪問靜態成員變數，無法訪問非靜態成員。
   ```cpp
   class MyClass {
   public:
       static void showCount() {
           std::cout << "Object count: " << objectCount << std::endl;
       }
   };
   ```

## 範例
```cpp
#include <iostream>

void demoStaticLocal() {
    static int counter = 0; // 靜態局部變數
    counter++;
    std::cout << "Counter: " << counter << std::endl;
}

static int globalVar = 5; // 靜態全局變數

class Example {
public:
    static int staticVar; // 靜態成員變數
    Example() { staticVar++; }
};

int Example::staticVar = 0; // 初始化靜態成員

int main() {
    demoStaticLocal(); // 輸出: Counter: 1
    demoStaticLocal(); // 輸出: Counter: 2

    std::cout << "Global Var: " << globalVar << std::endl; // 輸出: Global Var: 5

    Example obj1;
    Example obj2;
    std::cout << "Static Var: " << Example::staticVar << std::endl; // 輸出: Static Var: 2

    return 0;
}
```

## 解釋
- **常見陷阱**：
  - 靜態局部變數的初始化只執行一次，這可能會導致意外行為，特別是在多次調用函數時。
  - 靜態全局變數的範圍限制可能會造成與其他文件中同名變數的衝突。
  
- **注意事項**：
  - 在多執行緒環境中使用靜態變數時需小心，可能會導致競爭條件。
  - 靜態成員函數無法訪問非靜態成員變數或函數，因此需要注意類的設計。

## 總結
`static`關鍵字在C++中是控制變數生命週期和可見性的關鍵工具，了解其用法對於編寫高效且易於維護的代碼至關重要。