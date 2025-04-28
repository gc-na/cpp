<!--
Meta Description: # C++ 中的「friend」關鍵字：權限與封裝的橋樑 ## 概要 在 C++ 中，「friend」關鍵字用來宣告一個函數或類別可以訪問另一個類別的私有和保護成員，從而提供更靈活的封裝機制。 ## 文檔 ### 目的 「friend」關鍵字的主要目的是允許特定的函數或類別訪問類別的私有成員，這在需...
Meta Keywords: box, friend, width, printwidth, class
-->

# C++ 中的「friend」關鍵字：權限與封裝的橋樑

## 概要
在 C++ 中，「friend」關鍵字用來宣告一個函數或類別可以訪問另一個類別的私有和保護成員，從而提供更靈活的封裝機制。

## 文檔
### 目的
「friend」關鍵字的主要目的是允許特定的函數或類別訪問類別的私有成員，這在需要密切合作的類別之間非常有用。

### 使用方法
在 C++ 中，使用「friend」關鍵字時，需在類別內部進行宣告。以下是使用「friend」的基本語法：

```cpp
class ClassName {
    friend ReturnType functionName(parameters);
    friend class FriendClassName;
};
```

- **友元函數**：可以是類別外部的函數，能夠訪問該類別的私有和保護成員。
- **友元類別**：可以是另一個類別，該類別的所有成員函數都能訪問該類別的私有和保護成員。

### 詳細說明
- 被宣告為友元的函數或類別不會成為該類別的成員，因此它們不需要通過對象來訪問成員。
- 友元關係是單向的：如果類別 A 是類別 B 的友元，則 A 可以訪問 B 的私有成員，但 B 不能自動訪問 A 的成員。
- 友元關係不會影響封裝性，因為友元只是一種授權，而不是完整的訪問權限。

## 範例
以下是「friend」關鍵字的基本使用範例：

```cpp
#include <iostream>

class Box {
private:
    double width;

public:
    Box(double w) : width(w) {}

    // 宣告友元函數
    friend void printWidth(Box box);
};

// 定義友元函數
void printWidth(Box box) {
    std::cout << "Box width: " << box.width << std::endl;
}

int main() {
    Box box(10.0);
    printWidth(box); // 可以訪問 Box 的私有成員
    return 0;
}
```

在這個範例中，`printWidth` 函數可以訪問 `Box` 類別的私有成員 `width`。

## 解釋
### 常見陷阱
1. **友元函數和成員函數的區別**：友元函數不是類別的成員，因此不能直接使用 `this` 指針。
2. **友元關係的單向性**：如果一個類別是友元，並不意味著它的友元也對它有訪問權限。

### 附加說明
- 使用友元時需謹慎，過度使用可能會破壞封裝性，增加程式碼的耦合度。
- 友元的使用應該明確且有限，保持類別的內聚性。

## 一句總結
C++ 中的「friend」關鍵字允許特定函數或類別訪問其他類別的私有成員，增強了封裝的靈活性。