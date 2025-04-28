<!--
Meta Description: # C++ 中的 extern 關鍵字：用於變量和函數的聲明 ## 概述 `extern` 是 C++ 中一個重要的關鍵字，用於聲明變量和函數的外部鏈接性。它允許在一個翻譯單元中使用定義在另一個翻譯單元中的變量或函數，從而促進了模塊化編程和代碼重用。 ## 文檔 ### 目的 `extern` 的主...
Meta Keywords: extern, cpp, void, myfunction, myvariable
-->

# C++ 中的 extern 關鍵字：用於變量和函數的聲明

## 概述
`extern` 是 C++ 中一個重要的關鍵字，用於聲明變量和函數的外部鏈接性。它允許在一個翻譯單元中使用定義在另一個翻譯單元中的變量或函數，從而促進了模塊化編程和代碼重用。

## 文檔
### 目的
`extern` 的主要目的是告訴編譯器某個變量或函數的定義存在於其他地方，這樣在當前的翻譯單元中可以使用這些變量或函數，而不會造成重複定義的錯誤。

### 使用方法
在 C++ 中，`extern` 可以用於變量和函數的聲明。其語法如下：

- **變量聲明**:
  ```cpp
  extern int myVariable; // 聲明一個外部變量
  ```

- **函數聲明**:
  ```cpp
  extern void myFunction(); // 聲明一個外部函數
  ```

### 詳細說明
使用 `extern` 的變量或函數在其他翻譯單元中必須有相應的定義，否則在鏈接階段會出現錯誤。變量可以在任意一個翻譯單元中定義，通常在 `.cpp` 文件中，並且可以在多個文件中使用相同的聲明。

在 C++ 中，`extern` 也可以用來聲明 C 語言的函數或變量，這對於 C/C++ 混合編程特別有用。這是通過 `extern "C"` 實現的，語法如下：

```cpp
extern "C" {
    void cFunction(); // C 語言函數聲明
}
```

## 示例
### 基本使用示例
1. **變量示例**:
   ```cpp
   // file1.cpp
   int myVariable = 10; // 定義變量

   // file2.cpp
   extern int myVariable; // 聲明外部變量

   void printVariable() {
       std::cout << myVariable << std::endl; // 使用外部變量
   }
   ```

2. **函數示例**:
   ```cpp
   // file1.cpp
   void myFunction() {
       std::cout << "Hello from myFunction" << std::endl;
   }

   // file2.cpp
   extern void myFunction(); // 聲明外部函數

   void callFunction() {
       myFunction(); // 調用外部函數
   }
   ```

## 說明
使用 `extern` 時，開發者需要注意以下幾點：

- **鏈接錯誤**：如果在不同的翻譯單元中聲明了一個變量，但沒有提供其定義，則在鏈接階段會出現未定義參考的錯誤。
- **命名衝突**：如果多個翻譯單元中有相同名稱的 `extern` 變量，這可能導致命名衝突，開發者需要確保這些變量的唯一性。
- **作用域**：使用 `extern` 聲明的變量具有全局作用域，但在使用時仍需遵循 C++ 的作用域規則。

## 一行總結
`extern` 關鍵字用於在 C++ 中聲明外部變量和函數，以支持跨翻譯單元的代碼重用。