<!--
Meta Description: # C++ "extern" 關鍵字解釋及用法 ## 簡介 在 C++ 中，`extern` 是一個用於聲明變數或函數的關鍵字，主要用來指示這些變數或函數是在其他文件中定義的。這對於跨文件共享數據或函數非常有用。 ## 文檔 ### 目的 `extern` 的主要目的是讓編譯器知道某個變數或函數的定...
Meta Keywords: extern, cpp, int, globalvar, myfunction
-->

# C++ "extern" 關鍵字解釋及用法

## 簡介
在 C++ 中，`extern` 是一個用於聲明變數或函數的關鍵字，主要用來指示這些變數或函數是在其他文件中定義的。這對於跨文件共享數據或函數非常有用。

## 文檔
### 目的
`extern` 的主要目的是讓編譯器知道某個變數或函數的定義不在當前文件中，而是在其他地方。這樣可以避免重複定義的錯誤，並且讓不同的文件之間能夠合作使用資料。

### 用法
在使用 `extern` 時，通常是在頭文件中聲明變數或函數的原型，然後在某個實現文件中定義它們。這樣可以提高代碼的可重用性和組織性。

- **變數的聲明**:
```cpp
extern int globalVar; // 聲明一個全局變數
```

- **函數的聲明**:
```cpp
extern void myFunction(); // 聲明一個函數
```

在另一個文件中，你可以這樣定義全局變數或函數：
```cpp
int globalVar = 10; // 定義全局變數

void myFunction() {
    // 函數實現
}
```

## 示例
### 基本用法
以下是一個簡單的例子，展示如何使用 `extern` 來共享變數和函數。

**main.cpp**
```cpp
#include <iostream>

// 聲明外部變數和函數
extern int globalVar;
extern void myFunction();

int main() {
    std::cout << "Global Variable: " << globalVar << std::endl;
    myFunction();
    return 0;
}
```

**definitions.cpp**
```cpp
#include <iostream>

int globalVar = 42; // 定義全局變數

void myFunction() {
    std::cout << "Function called!" << std::endl;
}
```

當你編譯並運行這兩個文件時，將會看到以下輸出：
```
Global Variable: 42
Function called!
```

## 解釋
### 常見陷阱
- **未定義變數**: 如果你聲明了變數但沒有在任何地方定義它，當你編譯時會遇到鏈接錯誤。
- **作用域問題**: `extern` 變數的作用域是全局的，因此在不同的文件中使用時要小心命名衝突。
- **類型不匹配**: 確保在聲明和定義中使用相同的類型，否則會導致未定義行為。

### 額外注意事項
`extern` 也可以用於 C++ 中的類型和模板，適用於需要跨文件共享的情況，但在使用時一定要遵循正確的語法和結構。

## 一句話總結
`extern` 關鍵字在 C++ 中用於聲明在其他文件中定義的變數和函數，以便於跨文件共享和協作。