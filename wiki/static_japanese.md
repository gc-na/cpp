<!--
Meta Description: # C++における「static」の理解と使用法 ## 概要 C++の「static」は、変数や関数のスコープとライフタイムを制御するためのキーワードです。このキーワードは、変数が初期化されるタイミングやその可視性を変更するために使用されます。 ## ドキュメンテーション 「static」は主に3つ...
Meta Keywords: count, static, int, std, value
-->

# C++における「static」の理解と使用法

## 概要
C++の「static」は、変数や関数のスコープとライフタイムを制御するためのキーワードです。このキーワードは、変数が初期化されるタイミングやその可視性を変更するために使用されます。

## ドキュメンテーション
「static」は主に3つの文脈で使用されます：

1. **静的変数**: 関数内で宣言された静的変数は、その関数が呼ばれるたびに再初期化されず、プログラム全体を通して値を保持します。これは、関数が呼び出されるたびに状態を維持したい場合に便利です。

   ```cpp
   void function() {
       static int count = 0; // 最初の呼び出し時にのみ初期化される
       count++;
       std::cout << count << std::endl;
   }
   ```

2. **静的メンバー**: クラス内で宣言された静的メンバーは、クラスのインスタンスではなく、クラス自体に属します。これにより、すべてのインスタンスで共有されるデータを持つことができます。

   ```cpp
   class MyClass {
   public:
       static int count; // クラス全体で共有される変数
   };

   int MyClass::count = 0; // 静的メンバーの定義
   ```

3. **静的関数**: クラス内で静的に宣言された関数は、そのクラスのインスタンスに依存せずに呼び出すことができます。これにより、インスタンスにアクセスすることなく、クラスのデータにアクセスできます。

   ```cpp
   class MyClass {
   public:
       static void displayCount() {
           std::cout << "Count: " << count << std::endl;
       }
   };
   ```

## 例
以下は、C++における「static」の基本的な使用例です。

### 静的変数の例
```cpp
#include <iostream>

void increment() {
    static int value = 0; // 静的変数の初期化
    value++;
    std::cout << "Value: " << value << std::endl;
}

int main() {
    increment(); // 出力: Value: 1
    increment(); // 出力: Value: 2
    increment(); // 出力: Value: 3
    return 0;
}
```

### 静的メンバーの例
```cpp
#include <iostream>

class Counter {
public:
    static int count; // 静的メンバーの宣言

    Counter() {
        count++; // コンストラクタが呼ばれるたびにカウントを増加
    }
};

int Counter::count = 0; // 静的メンバーの定義

int main() {
    Counter a;
    Counter b;
    std::cout << "Total Count: " << Counter::count << std::endl; // 出力: Total Count: 2
    return 0;
}
```

### 静的関数の例
```cpp
#include <iostream>

class Math {
public:
    static int add(int a, int b) { // 静的関数
        return a + b;
    }
};

int main() {
    std::cout << "Sum: " << Math::add(5, 10) << std::endl; // 出力: Sum: 15
    return 0;
}
```

## 説明
「static」を使用する際の一般的な注意点や落とし穴があります。

- **初期化のタイミング**: 静的変数は、最初の呼び出し時に初期化されるため、関数が呼ばれない限り、値は設定されません。
- **スコープの制限**: 静的メンバーや関数は、そのクラスの外部からもアクセス可能ですが、インスタンスのメンバーにはアクセスできません。
- **スレッド安全性**: 静的変数がマルチスレッド環境で使用される場合、競合状態を避けるために適切な同期が必要です。

## 一文の要約
C++の「static」は、変数や関数のスコープとライフタイムを制御し、状態を保持したり、クラス全体でデータを共有するために使用されるキーワードです。