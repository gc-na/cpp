<!--
Meta Description: # C++ 中的 "private" 存取修飾符 ## 概述 在 C++ 中，`private` 是一種存取修飾符，用於控制類別成員的可見性與存取權限。當類別成員被標記為 `private` 時，只有該類別的成員函數和友元函數可以訪問這些成員，從而保護對象的內部狀態不被外部代碼隨意修改。 ## 文檔...
Meta Keywords: private, balance, void, account, bankaccount
-->

# C++ 中的 "private" 存取修飾符

## 概述
在 C++ 中，`private` 是一種存取修飾符，用於控制類別成員的可見性與存取權限。當類別成員被標記為 `private` 時，只有該類別的成員函數和友元函數可以訪問這些成員，從而保護對象的內部狀態不被外部代碼隨意修改。

## 文檔
### 目的
`private` 修飾符的主要目的是對類別的成員進行封裝，促進數據隱藏和保護，防止外部代碼直接訪問類別的內部狀態。

### 使用
在 C++ 中，`private` 修飾符通常放置在類別定義的開頭，後面跟隨著需要保護的成員變數或成員函數。以下是使用 `private` 修飾符的基本語法：

```cpp
class ClassName {
private:
    // 私有成員變數
    int privateVar;

    // 私有成員函數
    void privateMethod();
public:
    // 公有成員函數
    void publicMethod();
};
```

### 詳細說明
1. **存取控制**：`private` 成員無法被類別外部的代碼直接存取。這有助於保持類別內部的數據一致性和正確性。
2. **友元函數**：若某個函數需要訪問 `private` 成員，可以將其聲明為類別的友元函數，這樣它就可以直接訪問這些成員。
3. **繼承**：在類別繼承中，基類的 `private` 成員將無法在派生類中訪問，但可以通過公有或保護的成員函數進行訪問。

## 範例
以下是一個基本的範例，展示 `private` 修飾符的使用：

```cpp
#include <iostream>
using namespace std;

class BankAccount {
private:
    double balance; // 私有變數

public:
    BankAccount(double initialBalance) : balance(initialBalance) {}

    void deposit(double amount) {
        if (amount > 0) {
            balance += amount; // 可以訪問私有變數
        }
    }

    void displayBalance() {
        cout << "Balance: " << balance << endl; // 可以訪問私有變數
    }
};

int main() {
    BankAccount account(100.0);
    account.deposit(50.0);
    account.displayBalance();
    
    // 以下行會導致編譯錯誤，因為 balance 是私有的
    // cout << account.balance;

    return 0;
}
```

## 解釋
- **常見陷阱**：初學者可能會嘗試直接訪問 `private` 成員，這會導致編譯錯誤。應始終使用公有函數來操作私有成員。
- **友元函數的使用**：如果需要在類別外部的函數中訪問 `private` 成員，需小心使用友元函數，因為這可能會違背封裝的原則。

## 總結
`private` 修飾符是 C++ 中實現數據隱藏和封裝的重要工具，通過限制對類別內部成員的訪問，幫助開發者維護對象的完整性和安全性。