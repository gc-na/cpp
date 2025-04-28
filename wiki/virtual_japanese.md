<!--
Meta Description: # C++における「virtual」キーワードの解説 ## 概要 C++プログラミング言語における「virtual」キーワードは、動的ポリモーフィズムを実現するための重要な機能です。このキーワードを使用すると、基底クラスのポインタや参照を通じて、派生クラスのメンバー関数を呼び出すことが可能になります...
Meta Keywords: std, virtual, public, class, animal
-->

# C++における「virtual」キーワードの解説

## 概要
C++プログラミング言語における「virtual」キーワードは、動的ポリモーフィズムを実現するための重要な機能です。このキーワードを使用すると、基底クラスのポインタや参照を通じて、派生クラスのメンバー関数を呼び出すことが可能になります。

## ドキュメント
### 目的
「virtual」キーワードは、主にクラスのメンバー関数に適用され、派生クラスでオーバーライド可能にすることで、基底クラスのポインタや参照を介して派生クラスの関数を実行できるようにします。

### 使用法
`virtual`キーワードは、基底クラスの関数宣言の前に付けます。これにより、その関数が派生クラスでオーバーライドされることを示します。たとえば：

```cpp
class Base {
public:
    virtual void show() {
        std::cout << "Base class" << std::endl;
    }
};

class Derived : public Base {
public:
    void show() override {
        std::cout << "Derived class" << std::endl;
    }
};
```

### 詳細
- **仮想関数**: `virtual`キーワードを使って宣言された関数を仮想関数と呼びます。仮想関数は、基底クラスのポインタを通じて呼び出される場合、実行時に動的にどの関数が呼ばれるかが決まります。
- **オーバーライド**: 派生クラスで基底クラスの仮想関数を再定義することをオーバーライドと呼びます。この時、派生クラスの関数は`override`修飾子を使って明示的にオーバーライドされることを示すことが推奨されます。
- **デストラクタ**: 基底クラスのデストラクタも仮想にすることが推奨されます。これにより、派生クラスの適切なデストラクタが呼ばれ、リソースの適切な解放が保証されます。

## 例
以下は、`virtual`キーワードを使用した基本的な例です。

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
        std::cout << "Bark" << std::endl;
    }
};

class Cat : public Animal {
public:
    void sound() override {
        std::cout << "Meow" << std::endl;
    }
};

int main() {
    Animal* a1 = new Dog();
    Animal* a2 = new Cat();

    a1->sound(); // 出力: Bark
    a2->sound(); // 出力: Meow

    delete a1;
    delete a2;

    return 0;
}
```

## 解説
- **共通の落とし穴**: 仮想関数を正しく使用しない場合、予期しない動作が発生することがあります。特に、基底クラスのデストラクタが仮想でない場合、リソースリークが発生する可能性があります。
- **性能への影響**: 仮想関数は、通常の関数呼び出しよりもオーバーヘッドがあるため、パフォーマンスに影響を与える場合があります。ただし、この影響は通常、ポリモーフィズムの利点によって相殺されます。

## 一文要約
C++における「virtual」キーワードは、動的ポリモーフィズムを実現するために使用され、基底クラスのポインタを通じて派生クラスの関数を呼び出すことを可能にします。