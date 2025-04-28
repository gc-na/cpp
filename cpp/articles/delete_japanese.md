<!--
Meta Description: # C++のdelete演算子: メモリ管理の基本 ## 概要 C++における`delete`演算子は、動的に確保されたメモリを解放するために使用されます。これにより、メモリリークを防ぎ、プログラムの効率を向上させることができます。 ## ドキュメンテーション `delete`演算子は、C++のメモ...
Meta Keywords: delete, myclass, new, cpp, obj
-->

# C++のdelete演算子: メモリ管理の基本

## 概要
C++における`delete`演算子は、動的に確保されたメモリを解放するために使用されます。これにより、メモリリークを防ぎ、プログラムの効率を向上させることができます。

## ドキュメンテーション
`delete`演算子は、C++のメモリ管理において重要な役割を果たします。動的メモリは、`new`演算子を使用して割り当てられますが、使用が終わった後は必ず`delete`を使用して解放する必要があります。これにより、メモリリークを防ぎ、プログラムのメモリ使用量を最適化します。

### 使用法
- 単一オブジェクトの場合:
  ```cpp
  MyClass* obj = new MyClass();
  delete obj; // objが指すメモリを解放
  ```

- 配列の場合:
  ```cpp
  MyClass* arr = new MyClass[10];
  delete[] arr; // 配列全体のメモリを解放
  ```

`delete`と`delete[]`の使い分けは非常に重要です。単一のオブジェクトには`delete`を使用し、配列には`delete[]`を使用する必要があります。誤って`delete`を配列に使用すると、未定義の動作を引き起こす可能性があります。

## 例
### 1. 単一オブジェクトの削除
```cpp
#include <iostream>

class MyClass {
public:
    MyClass() { std::cout << "Constructor\n"; }
    ~MyClass() { std::cout << "Destructor\n"; }
};

int main() {
    MyClass* obj = new MyClass(); // 動的メモリの確保
    delete obj; // メモリの解放
    return 0;
}
```

### 2. 配列の削除
```cpp
#include <iostream>

class MyClass {
public:
    MyClass() { std::cout << "Constructor\n"; }
    ~MyClass() { std::cout << "Destructor\n"; }
};

int main() {
    MyClass* arr = new MyClass[3]; // 動的配列の確保
    delete[] arr; // メモリの解放
    return 0;
}
```

## 説明
`delete`演算子を使用する際の一般的な落とし穴には、以下の点があります。

1. **二重解放**: 同じメモリ領域を二度解放しようとすると、プログラムがクラッシュすることがあります。`delete`を実行した後は、ポインタを`nullptr`に設定することが推奨されます。

2. **未初期化ポインタ**: 未初期化のポインタを`delete`すると、未定義の動作が発生します。常に有効なポインタを解放するように心がけましょう。

3. **配列の削除ミス**: 単一オブジェクトに対して`delete[]`を使用すると、正しくメモリを解放できず、未定義の動作を引き起こします。

## 一文まとめ
C++の`delete`演算子は、動的メモリを解放するための重要なツールであり、適切に使用することでメモリリークを防げます。