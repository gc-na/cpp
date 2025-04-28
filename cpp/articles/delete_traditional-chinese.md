<!--
Meta Description: # C++ 中的 delete 關鍵字：記憶體管理的重要工具 ## 概述 在 C++ 中，`delete` 關鍵字用於釋放之前使用 `new` 申請的動態記憶體。這是 C++ 提供的記憶體管理機制的一部分，能夠有效避免記憶體洩漏和其他記憶體管理問題。 ## 文檔 ### 目的 `delete` 的主...
Meta Keywords: delete, myclass, arr, new, cpp
-->

# C++ 中的 delete 關鍵字：記憶體管理的重要工具

## 概述
在 C++ 中，`delete` 關鍵字用於釋放之前使用 `new` 申請的動態記憶體。這是 C++ 提供的記憶體管理機制的一部分，能夠有效避免記憶體洩漏和其他記憶體管理問題。

## 文檔
### 目的
`delete` 的主要目的是釋放動態分配的記憶體，確保程序在結束時不會留下未使用的記憶體佔用。透過正確使用 `delete`，開發者可以維護應用程式的性能和穩定性。

### 用法
在 C++ 中，`delete` 有兩種使用方式：
1. **釋放單一物件的記憶體**：
   ```cpp
   Type* ptr = new Type();
   // 使用 ptr 進行操作
   delete ptr;  // 釋放 ptr 指向的記憶體
   ```

2. **釋放陣列的記憶體**：
   ```cpp
   Type* arr = new Type[size];
   // 使用 arr 進行操作
   delete[] arr;  // 釋放 arr 指向的陣列記憶體
   ```

### 詳細說明
- **基本語法**：
  - `delete pointer;`：釋放單一物件的記憶體。
  - `delete[] pointer;`：釋放動態分配的陣列記憶體。
  
- **注意事項**：
  - 在釋放記憶體之前，確保指標是有效的，且不為 `nullptr`。呼叫 `delete` 或 `delete[]` 對 `nullptr` 不會造成錯誤。
  - 釋放後，指標會成為懸空指標，建議立即將其設為 `nullptr`。

## 示例
### 釋放單一物件的記憶體
```cpp
#include <iostream>
class MyClass {
public:
    MyClass() { std::cout << "MyClass created\n"; }
    ~MyClass() { std::cout << "MyClass destroyed\n"; }
};

int main() {
    MyClass* obj = new MyClass();  // 動態分配
    delete obj;                    // 釋放記憶體
    return 0;
}
```

### 釋放陣列的記憶體
```cpp
#include <iostream>

int main() {
    int* arr = new int[5];  // 動態分配陣列
    delete[] arr;           // 釋放陣列記憶體
    return 0;
}
```

## 說明
- **常見陷阱**：
  - **重複釋放**：同一指標不能被多次釋放，這會導致未定義行為。
  - **未釋放記憶體**：若未正確使用 `delete`，將會導致記憶體洩漏，長時間運行的應用程式可能因此耗盡記憶體。

- **建議**：
  - 使用智能指標（如 `std::unique_ptr` 或 `std::shared_ptr`）來自動管理記憶體，這樣可以減少手動釋放記憶體的需要，從而降低錯誤的風險。

## 總結
`delete` 是 C++ 中一個關鍵的記憶體管理工具，正確使用它可以防止記憶體洩漏並確保應用程式的穩定性。