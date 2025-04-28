<!--
Meta Description: # 在 C++ 中的虛擬 (virtual) 關鍵字 ## 概述 在 C++ 中，`virtual` 關鍵字用於定義虛擬函數，這是實現多態性的重要機制。虛擬函數允許子類別重寫父類別的函數，從而在運行時根據對象的實際類型來調用相應的函數。 ## 文檔 ### 目的 `virtual` 關鍵字的主要目的...
Meta Keywords: virtual, std, animal, public, speak
-->

# 在 C++ 中的虛擬 (virtual) 關鍵字

## 概述
在 C++ 中，`virtual` 關鍵字用於定義虛擬函數，這是實現多態性的重要機制。虛擬函數允許子類別重寫父類別的函數，從而在運行時根據對象的實際類型來調用相應的函數。

## 文檔
### 目的
`virtual` 關鍵字的主要目的是支持運行時多態性，這樣可以通過基類的指標或引用來調用衍生類中的重寫函數。

### 使用
在類中聲明函數為虛擬函數時，需要在函數前加上 `virtual` 關鍵字。當類的某個函數被聲明為虛擬時，該類的所有衍生類都可以重寫該函數，並且在使用基類指標或引用調用該函數時，將根據對象的實際類型選擇正確的版本。

### 詳細說明
1. **虛擬函數**：通過在基類中使用 `virtual` 關鍵字來聲明虛擬函數。
2. **純虛擬函數**：如果希望在基類中定義一個不具體實現的虛擬函數，可以將其聲明為純虛擬函數，格式為 `virtual void functionName() = 0;`。
3. **虛擬表（vtable）**：每個包含虛擬函數的類都有一個虛擬表，該表包含指向虛擬函數的指針。
4. **虛擬析構函數**：如果類中有虛擬函數，則應使用虛擬析構函數以確保正確釋放資源。

## 範例
以下是一個簡單的範例，展示如何使用 `virtual` 關鍵字。

```cpp
#include <iostream>

class Animal {
public:
    virtual void speak() {
        std::cout << "動物發出聲音" << std::endl;
    }
};

class Dog : public Animal {
public:
    void speak() override {
        std::cout << "狗叫: 汪汪!" << std::endl;
    }
};

class Cat : public Animal {
public:
    void speak() override {
        std::cout << "貓叫: 喵喵!" << std::endl;
    }
};

int main() {
    Animal* animal1 = new Dog();
    Animal* animal2 = new Cat();

    animal1->speak(); // 輸出: 狗叫: 汪汪!
    animal2->speak(); // 輸出: 貓叫: 喵喵!

    delete animal1;
    delete animal2;

    return 0;
}
```

## 解釋
1. **常見陷阱**：
   - 忘記在基類中將析構函數聲明為虛擬會導致資源釋放不當。
   - 在衍生類中未正確重寫虛擬函數（尤其是忽略 `override` 關鍵字）。
   
2. **注意事項**：
   - 使用 `override` 關鍵字來確保重寫的正確性。
   - 多重繼承時需小心虛擬函數的調用，可能導致二義性。

## 一句總結
`virtual` 關鍵字在 C++ 中用於定義虛擬函數，使得基類指標能夠調用衍生類中的重寫函數，實現運行時多態性。