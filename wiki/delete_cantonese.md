<!--
Meta Description: # C++ 中的 "delete" 關鍵字：記憶體管理的核心 ## 概述 在 C++ 中，`delete` 是一個關鍵字，用於釋放動態分配的記憶體。它是管理資源的重要工具，幫助開發者避免記憶體泄漏，並確保有效的記憶體使用。 ## 文件說明 ### 目的 `delete` 的主要目的是釋放之前使用 `...
Meta Keywords: delete, myclass, new, obj, arr
-->

# C++ 中的 "delete" 關鍵字：記憶體管理的核心

## 概述
在 C++ 中，`delete` 是一個關鍵字，用於釋放動態分配的記憶體。它是管理資源的重要工具，幫助開發者避免記憶體泄漏，並確保有效的記憶體使用。

## 文件說明
### 目的
`delete` 的主要目的是釋放之前使用 `new` 關鍵字分配的記憶體。當不再需要某個物件或數據時，使用 `delete` 可以將其記憶體歸還給系統。

### 使用方法
- **單一物件的釋放**：使用 `delete` 釋放動態分配的單一物件。
- **數組的釋放**：使用 `delete[]` 釋放動態分配的數組。

### 詳細信息
- 當使用 `new` 創建物件時，記憶體會在堆上分配。這種記憶體不會自動釋放，必須手動釋放。
- 使用 `delete` 釋放單一物件：
  ```cpp
  MyClass* obj = new MyClass();
  delete obj;  // 釋放 obj 的記憶體
  ```
- 使用 `delete[]` 釋放數組：
  ```cpp
  MyClass* arr = new MyClass[10];
  delete[] arr;  // 釋放 arr 的記憶體
  ```

## 示例
以下是一些基本用法的示例：

### 釋放單一物件
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    MyClass() { cout << "Constructor called!" << endl; }
    ~MyClass() { cout << "Destructor called!" << endl; }
};

int main() {
    MyClass* obj = new MyClass(); // 動態分配
    delete obj; // 釋放記憶體
    return 0;
}
```

### 釋放數組
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    MyClass() { cout << "Constructor called!" << endl; }
    ~MyClass() { cout << "Destructor called!" << endl; }
};

int main() {
    MyClass* arr = new MyClass[5]; // 動態分配數組
    delete[] arr; // 釋放數組的記憶體
    return 0;
}
```

## 解釋
### 常見陷阱
1. **重複釋放**：對同一指標調用 `delete` 或 `delete[]` 會導致未定義行為。確保每個指標只被釋放一次。
2. **未釋放記憶體**：如果不使用 `delete` 釋放動態分配的記憶體，將會產生記憶體泄漏。
3. **使用未定義的指標**：在釋放記憶體後，不要再使用指向已釋放記憶體的指標。最好在釋放後將指標設置為 `nullptr`。

## 一行總結
`delete` 是 C++ 中用於釋放動態分配記憶體的關鍵字，確保資源管理的有效性。