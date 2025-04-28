<!--
Meta Description: # C++中的explicit關鍵字：用途與範例 ## 摘要 在C++中，`explicit`是一個關鍵字，用於防止編譯器自動將某些類型轉換成其他類型，特別是在構造函數和轉換運算符中，確保類型轉換是明確且安全的。 ## 文檔 ### 目的 `explicit`的主要目的是防止不必要的隱式類型轉換，這...
Meta Keywords: explicit, distance, meters, int, cpp
-->

# C++中的explicit關鍵字：用途與範例

## 摘要
在C++中，`explicit`是一個關鍵字，用於防止編譯器自動將某些類型轉換成其他類型，特別是在構造函數和轉換運算符中，確保類型轉換是明確且安全的。

## 文檔
### 目的
`explicit`的主要目的是防止不必要的隱式類型轉換，這樣可以減少錯誤和不易察覺的行為。當一個構造函數被標記為`explicit`，只有在顯式調用時，該構造函數才能被使用。這樣可以強迫開發者在轉換時提供明確的意圖。

### 使用
`explicit`關鍵字只能用於構造函數和轉換運算符。當用於構造函數時，這意味著該構造函數不能被隱式調用，必須使用顯式初始化。

#### 語法
```cpp
class ClassName {
public:
    explicit ClassName(Type parameter);
};
```

### 詳細說明
- 當使用`explicit`關鍵字時，對於單一參數的構造函數，編譯器不會自動進行轉換。
- 若一個類中有多個構造函數，標記某些構造函數為`explicit`可以提供更好的控制，避免意外的隱式轉換。
- 在使用轉換運算符時，`explicit`同樣防止了隱式轉換，確保轉換的明確性。

## 範例
```cpp
#include <iostream>

class Distance {
public:
    explicit Distance(int meters) : meters(meters) {}
    
    int getMeters() const { return meters; }

private:
    int meters;
};

int main() {
    Distance d1(5); // 正確的用法
    // Distance d2 = 5; // 錯誤：不能隱式轉換
    Distance d3 = Distance(5); // 正確的顯式轉換
    std::cout << "Distance: " << d1.getMeters() << " meters" << std::endl;
    return 0;
}
```

## 解釋
在使用`explicit`時，常見的陷阱包括：
- 忘記在需要明確轉換的地方使用`explicit`關鍵字，可能導致不必要的隱式轉換。
- 對於多參數構造函數，`explicit`不會影響隱式轉換，僅適用於單參數構造函數。
- 如果不希望類型自動轉換，所有相關的構造函數都應該標記為`explicit`。

## 總結
`explicit`關鍵字在C++中用於防止不必要的隱式轉換，以提升代碼的可讀性和安全性。