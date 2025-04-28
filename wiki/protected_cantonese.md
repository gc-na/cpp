<!--
Meta Description: # C++ 中的「protected」關鍵字：使用、示例及注意事項 ## 簡介 在 C++ 中，「protected」是一個訪問控制關鍵字，用於指定類成員的可見性。這個關鍵字對於繼承和封裝的實現至關重要，使得子類可以訪問基類的某些成員而不必將其公開給所有其他類。 ## 文檔 ### 目的 「prot...
Meta Keywords: protected, public, class, void, animal
-->

# C++ 中的「protected」關鍵字：使用、示例及注意事項

## 簡介
在 C++ 中，「protected」是一個訪問控制關鍵字，用於指定類成員的可見性。這個關鍵字對於繼承和封裝的實現至關重要，使得子類可以訪問基類的某些成員而不必將其公開給所有其他類。

## 文檔
### 目的
「protected」關鍵字的主要目的是為了管理類成員的訪問權限，使得在繼承階層中，子類別可以訪問基類的成員，但同時防止外部類別直接訪問這些成員。

### 使用
在類定義中，使用「protected」關鍵字來標記成員變量或方法。這些標記為「protected」的成員只能由該類及其子類訪問，但無法被其他類直接訪問。

### 詳細說明
- **語法**：
  ```cpp
  class Base {
  protected:
      int protectedVar;
      void protectedMethod() { /* ... */ }
  };
  
  class Derived : public Base {
  public:
      void accessBase() {
          protectedVar = 10; // 允許訪問
          protectedMethod();  // 允許訪問
      }
  };
  
  class Other {
  public:
      void accessBase() {
          Base b;
          // b.protectedVar = 10; // 錯誤：無法訪問
      }
  };
  ```

## 示例
以下是使用「protected」的基本示例：

```cpp
#include <iostream>
using namespace std;

class Animal {
protected:
    string name;
public:
    Animal(string n) : name(n) {}
};

class Dog : public Animal {
public:
    Dog(string n) : Animal(n) {}
    void bark() {
        cout << name << " says woof!" << endl; // 訪問基類的 protected 成員
    }
};

int main() {
    Dog myDog("Buddy");
    myDog.bark(); // 輸出 "Buddy says woof!"
    return 0;
}
```

## 解釋
### 常見問題及注意事項
1. **無法從非子類訪問**：即使在同一命名空間中，非子類無法訪問「protected」成員。
2. **與 public 和 private 的區別**：「protected」允許子類訪問，而「private」則不允許，即使是子類也無法訪問私有成員。
3. **多重繼承的情況**：在多重繼承中，確保「protected」成員不會因為不同的基類而引起混淆。

## 一句話總結
「protected」關鍵字在 C++ 中用於控制類成員的訪問權限，允許子類訪問基類的某些成員，但阻止其他類直接訪問。