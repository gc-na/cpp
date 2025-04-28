<!--
Meta Description: # C++ 中的 "public" 關鍵字：用途與示例 ## 簡介 在 C++ 中，`public` 是一個存取修飾符，用於指定類別成員的可見性。它決定了哪些類別或函數可以訪問特定的成員，從而影響對物件數據的封裝和數據隱私。 ## 文檔 ### 目的 `public` 關鍵字的主要目的是提供對類別成...
Meta Keywords: public, person, name, protected, private
-->

# C++ 中的 "public" 關鍵字：用途與示例

## 簡介
在 C++ 中，`public` 是一個存取修飾符，用於指定類別成員的可見性。它決定了哪些類別或函數可以訪問特定的成員，從而影響對物件數據的封裝和數據隱私。

## 文檔
### 目的
`public` 關鍵字的主要目的是提供對類別成員的公開訪問權限，使得外部代碼能夠直接訪問這些成員。這通常用於需要被外界直接使用的屬性和方法。

### 用法
在定義類別時，可以將成員變數和成員函數標記為 `public`，以便其他類別或函數可以訪問它們。`public` 部分通常位於類別的開頭或中間，並以 `public:` 標記。

### 詳細說明
- **存取修飾符**：C++ 提供了三種存取修飾符：`public`、`protected` 和 `private`。`public` 成員可以被任何其他代碼訪問，而 `private` 成員只能在類內部訪問，`protected` 則允許子類訪問。
- **使用範例**：在使用 `public` 成員時，可以直接創建類的實例並調用其成員函數或訪問其變數。
- **注意事項**：雖然 `public` 使得成員可被外部訪問，但這也可能導致數據被不當修改，因此在設計時需要謹慎考慮。

## 示例
以下是一個簡單的 C++ 類別示例，展示了 `public` 成員的用法：

```cpp
#include <iostream>
using namespace std;

class Person {
public:
    string name;

    void greet() {
        cout << "Hello, my name is " << name << "!" << endl;
    }
};

int main() {
    Person person;
    person.name = "Alice"; // 訪問 public 成員
    person.greet(); // 調用 public 方法
    return 0;
}
```

## 說明
- **常見陷阱**：使用 `public` 成員時，必須小心數據的完整性。如果允許外部代碼隨意修改內部狀態，可能會導致難以追蹤的錯誤。
- **設計考量**：在設計類別時，應該考慮是否確實需要將某些成員設為 `public`。通常，應該將大部分成員設為 `private` 或 `protected`，並通過 `public` 方法提供必要的訪問。

## 單行摘要
在 C++ 中，`public` 是一個存取修飾符，用於定義類別成員的公開可見性，允許外部訪問和操作這些成員。