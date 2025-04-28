<!--
Meta Description: # C++ 中的 protected 關鍵字：使用與注意事項 ## 概述 在 C++ 中，`protected` 是一種存取修飾符，用於控制類別成員的可見性。它允許類別和衍生類別之間的特定成員訪問，增強了對封裝的支持。 ## 文檔 ### 目的 `protected` 關鍵字的主要目的是限制成員變數...
Meta Keywords: protected, base, int, protectedvar, public
-->

# C++ 中的 protected 關鍵字：使用與注意事項

## 概述
在 C++ 中，`protected` 是一種存取修飾符，用於控制類別成員的可見性。它允許類別和衍生類別之間的特定成員訪問，增強了對封裝的支持。

## 文檔
### 目的
`protected` 關鍵字的主要目的是限制成員變數和成員函數的訪問權限，使其只能被類別自身及其派生類別訪問，這有助於保護數據並促進封裝。

### 使用
在 C++ 中，`protected` 修飾符可以用於類別的成員變數和成員函數。當一個成員被標記為 `protected`，它可以在該類別內部以及所有從該類別繼承的類別中被訪問。

#### 範例
```cpp
class Base {
protected:
    int protectedVar;

public:
    Base() : protectedVar(0) {}
};

class Derived : public Base {
public:
    void setProtectedVar(int value) {
        protectedVar = value; // 可以訪問 Base 類的 protected 成員
    }

    int getProtectedVar() {
        return protectedVar; // 可以訪問 Base 類的 protected 成員
    }
};

int main() {
    Derived d;
    d.setProtectedVar(10);
    return d.getProtectedVar(); // 輸出 10
}
```

## 解釋
在使用 `protected` 的時候，需要注意以下幾點：

1. **訪問限制**：`protected` 成員不能在類別外部直接訪問。這意味著即使是同一個類別的實例也無法直接訪問 `protected` 成員。
   
2. **繼承**：派生類別可以訪問基類中的 `protected` 成員，但只有在通過派生類的成員函數進行訪問時。

3. **友元類別**：友元類別或函數仍然可以訪問 `protected` 成員。

4. **與 private 的區別**：`private` 成員只能在類別內部訪問，而 `protected` 成員在派生類中也可以訪問，這使得 `protected` 成員在繼承場景中非常有用。

5. **默認情況**：在使用 `protected` 繼承時，基類的 `protected` 和 `public` 成員會保持其可見性，但 `private` 成員無法被訪問。

## 一句總結
在 C++ 中，使用 `protected` 可以有效地控制成員的訪問權限，從而增強數據的封裝性和安全性。