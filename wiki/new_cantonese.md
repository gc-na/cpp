<!--
Meta Description: # C++ 中的 "new" 關鍵字：動態記憶體分配 ## 簡介 在 C++ 中，`new` 是一個關鍵字，用於動態記憶體分配。它可以在運行時為對象或數組分配內存，並返回指向該內存的指針。 ## 文檔 ### 目的 `new` 關鍵字的主要用途是為對象或數組動態分配內存。這意味著內存的分配不是在編譯...
Meta Keywords: new, myclass, delete, std, int
-->

# C++ 中的 "new" 關鍵字：動態記憶體分配

## 簡介
在 C++ 中，`new` 是一個關鍵字，用於動態記憶體分配。它可以在運行時為對象或數組分配內存，並返回指向該內存的指針。

## 文檔
### 目的
`new` 關鍵字的主要用途是為對象或數組動態分配內存。這意味著內存的分配不是在編譯時決定的，而是根據程序的運行狀態進行分配。

### 使用方法
在 C++ 中，使用 `new` 關鍵字的基本語法如下：

```cpp
Type* pointerName = new Type;
```

這裡，`Type` 是要創建的對象的類型，`pointerName` 是指向該對象的指針。

對於數組的分配，語法如下：

```cpp
Type* pointerName = new Type[arraySize];
```

### 詳細信息
- `new` 會自動調用構造函數來初始化對象，並返回指向新分配內存的指針。
- 相應地，使用 `delete` 關鍵字來釋放通過 `new` 分配的內存，防止內存泄漏。
- 在使用 `new` 時，必須確保在不再使用指針時，調用 `delete` 來釋放內存。

## 示例
### 基本用法示例
```cpp
#include <iostream>

class MyClass {
public:
    MyClass() {
        std::cout << "MyClass constructor called!" << std::endl;
    }
    ~MyClass() {
        std::cout << "MyClass destructor called!" << std::endl;
    }
};

int main() {
    // 使用 new 創建對象
    MyClass* obj = new MyClass();
    
    // 使用 obj 進行操作...

    // 別忘了釋放內存
    delete obj;
    return 0;
}
```

### 數組的使用示例
```cpp
#include <iostream>

int main() {
    // 使用 new 創建整數數組
    int* arr = new int[5];

    // 初始化數組
    for (int i = 0; i < 5; ++i) {
        arr[i] = i * 10;
    }

    // 輸出數組元素
    for (int i = 0; i < 5; ++i) {
        std::cout << arr[i] << std::endl;
    }

    // 釋放數組內存
    delete[] arr;
    return 0;
}
```

## 解釋
在使用 `new` 進行動態內存分配時，開發者需要注意以下幾點：
- 確保在適當的時候使用 `delete` 來釋放內存，否則會導致內存泄漏。
- 如果使用 `new` 分配數組，必須使用 `delete[]` 來釋放內存，否則會導致未定義行為。
- 使用 `new` 可能會導致內存分配失敗，這時會返回 `nullptr`，建議檢查指針是否為 `nullptr`。

## 總結
在 C++ 中，`new` 關鍵字用於動態分配內存，開發者需要小心內存管理以避免內存泄漏。