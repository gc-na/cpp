<!--
Meta Description: # C++ 中的 "new" 關鍵字：動態記憶體分配的基礎 ## 摘要 在 C++ 中，`new` 是一個關鍵字，用於動態地分配記憶體。它使開發者能夠在執行時期創建物件，並且在不需要時可以釋放這些物件所佔用的記憶體。 ## 文檔 ### 目的 `new` 操作符的主要目的是在堆（heap）上動態分配...
Meta Keywords: new, delete, std, myclass, typename
-->

# C++ 中的 "new" 關鍵字：動態記憶體分配的基礎

## 摘要
在 C++ 中，`new` 是一個關鍵字，用於動態地分配記憶體。它使開發者能夠在執行時期創建物件，並且在不需要時可以釋放這些物件所佔用的記憶體。

## 文檔
### 目的
`new` 操作符的主要目的是在堆（heap）上動態分配記憶體，以創建物件或數組，這樣可以在程式的運行過程中根據需要動態增減記憶體的使用。

### 使用
在 C++ 中，使用 `new` 關鍵字的基本語法如下：

```cpp
TypeName* pointerVariable = new TypeName;
```

這會在堆上分配足夠的記憶體來存儲一個 `TypeName` 類型的物件，並返回該物件的地址。用於數組的語法如下：

```cpp
TypeName* pointerVariable = new TypeName[arraySize];
```

這會分配一個包含 `arraySize` 個 `TypeName` 類型物件的數組。

### 詳細說明
- **初始化**: 使用 `new` 分配的物件會調用其構造函數，確保物件被正確初始化。
- **釋放記憶體**: 使用 `new` 分配的記憶體需要使用 `delete` 來釋放。對於數組，需要使用 `delete[]`。

```cpp
delete pointerVariable;        // 釋放單一物件
delete[] pointerVariable;      // 釋放數組
```

- **錯誤處理**: 如果記憶體分配失敗，`new` 會拋出 `std::bad_alloc` 異常，除非使用 `new(nothrow)`，此時返回 `nullptr`。

## 範例
### 基本用法範例
```cpp
#include <iostream>

class MyClass {
public:
    MyClass() { std::cout << "Constructor called!" << std::endl; }
    ~MyClass() { std::cout << "Destructor called!" << std::endl; }
};

int main() {
    // 使用 new 分配單一物件
    MyClass* obj = new MyClass();
    
    // 使用 new 分配數組
    MyClass* objArray = new MyClass[2];
    
    // 釋放記憶體
    delete obj;
    delete[] objArray;

    return 0;
}
```

## 解釋
### 常見陷阱
- **記憶體洩漏**: 忘記釋放使用 `new` 分配的記憶體會導致記憶體洩漏。使用智能指針如 `std::unique_ptr` 或 `std::shared_ptr` 可以幫助自動管理記憶體。
- **多重釋放**: 將同一指標多次傳遞給 `delete` 會導致未定義行為。
- **使用已釋放的指標**: 在釋放記憶體後仍然使用該指標會導致崩潰或未定義的行為，應將指標設置為 `nullptr`。

## 一句總結
C++ 中的 `new` 關鍵字用於在執行時期動態分配記憶體，並且必須小心管理以防止記憶體洩漏。