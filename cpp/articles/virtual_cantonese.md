<!--
Meta Description: # C++ 中的「virtual」關鍵字：用途與實現 ## 簡介 在 C++ 中，「virtual」關鍵字用於實現多態性，允許程序在運行時根據對象的實際類型來調用適當的函數。這對於面向對象編程至關重要，因為它使得可以使用基類指針來調用派生類的函數。 ## 文檔 ### 目的 「virtual」關鍵字...
Meta Keywords: std, virtual, public, class, void
-->

# C++ 中的「virtual」關鍵字：用途與實現

## 簡介
在 C++ 中，「virtual」關鍵字用於實現多態性，允許程序在運行時根據對象的實際類型來調用適當的函數。這對於面向對象編程至關重要，因為它使得可以使用基類指針來調用派生類的函數。

## 文檔
### 目的
「virtual」關鍵字主要用於基類中的成員函數，標記該函數可以被派生類重寫。這樣做的好處是可以根據對象的實際類型來確定要調用的函數，從而實現多態性。

### 用法
要聲明一個虛擬函數，只需在基類的函數聲明前加上「virtual」關鍵字。當派生類重寫這個函數時，基類指針或引用調用該函數時，將會調用派生類的實現。

```cpp
class Base {
public:
    virtual void show() {
        std::cout << "Base class show function called." << std::endl;
    }
};

class Derived : public Base {
public:
    void show() override {
        std::cout << "Derived class show function called." << std::endl;
    }
};
```

### 詳細說明
1. **虛擬函數表**：當一個類包含虛擬函數時，編譯器會為該類創建一個虛擬函數表（vtable），並為每個對象創建一個指向該表的指針（vptr）。這使得在運行時能夠正確地解析函數調用。
  
2. **純虛擬函數**：如果一個虛擬函數沒有實現，可以將其聲明為純虛擬函數，這樣該類就成為抽象類，不能被實例化。純虛擬函數的語法為：「virtual void functionName() = 0;」。

3. **重寫**：在派生類中，重寫虛擬函數時可以使用「override」關鍵字，以提高代碼的可讀性和安全性。

## 範例
以下是一個簡單的示例，演示了如何使用虛擬函數實現多態性：

```cpp
#include <iostream>

class Animal {
public:
    virtual void sound() {
        std::cout << "Animal sound" << std::endl;
    }
};

class Dog : public Animal {
public:
    void sound() override {
        std::cout << "Woof!" << std::endl;
    }
};

class Cat : public Animal {
public:
    void sound() override {
        std::cout << "Meow!" << std::endl;
    }
};

int main() {
    Animal* a1 = new Dog();
    Animal* a2 = new Cat();
    
    a1->sound(); // 輸出 "Woof!"
    a2->sound(); // 輸出 "Meow!"
    
    delete a1;
    delete a2;
    return 0;
}
```

## 解釋
- **常見陷阱**：如果在基類中未使用「virtual」關鍵字，則即使派生類重寫了該函數，基類指針仍然會調用基類版本的函數。
  
- **虛擬析構函數**：當類中有虛擬函數時，建議也將析構函數設為虛擬，以確保派生類的析構函數被正確調用，避免資源泄漏。

- **性能考量**：使用虛擬函數會引入額外的性能開銷，因為需要通過 vtable 進行查找。

## 總結
在 C++ 中，使用「virtual」關鍵字可以實現運行時多態性，允許基類指針調用派生類的函數，這是面向對象編程的一個重要特性。