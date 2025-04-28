<!--
Meta Description: # C++의 explicit 키워드: 명시적 생성자와 변환 ## 개요 C++에서 `explicit` 키워드는 생성자가 단일 인수를 사용하여 암묵적인 타입 변환을 방지하는 데 사용됩니다. 이를 통해 프로그래머는 의도하지 않은 변환을 예방하고 코드의 명확성을 높일 수 있습...
Meta Keywords: myclass, explicit, value, int, 암묵적
-->

# C++의 explicit 키워드: 명시적 생성자와 변환

## 개요
C++에서 `explicit` 키워드는 생성자가 단일 인수를 사용하여 암묵적인 타입 변환을 방지하는 데 사용됩니다. 이를 통해 프로그래머는 의도하지 않은 변환을 예방하고 코드의 명확성을 높일 수 있습니다.

## 문서화
`explicit` 키워드는 클래스의 생성자 또는 변환 연산자 앞에 사용되어, 해당 생성자나 연산자가 암묵적으로 호출되는 것을 방지합니다. 기본적으로 C++에서는 단일 인수를 가진 생성자를 통해 자동으로 타입 변환이 이루어질 수 있지만, `explicit` 키워드를 사용하면 이를 명시적으로 호출해야만 변환이 가능하게 됩니다.

### 목적
- 암묵적인 타입 변환을 방지하여 의도하지 않은 행동을 막음
- 코드의 가독성을 높이고 명확성을 제공

### 사용법
`explicit` 키워드는 생성자 또는 변환 연산자 선언 시에 다음과 같이 사용됩니다:

```cpp
class MyClass {
public:
    explicit MyClass(int value);
};
```

이렇게 선언된 `MyClass`의 생성자는 `int` 타입의 인수를 명시적으로 제공해야만 객체를 생성할 수 있습니다. 예를 들어:

```cpp
MyClass obj1(10); // 유효
MyClass obj2 = 10; // 오류: 암묵적 변환 불가
```

## 예제
다음은 `explicit` 키워드의 기본 사용 예입니다.

```cpp
#include <iostream>

class MyClass {
public:
    explicit MyClass(int value) {
        std::cout << "Value: " << value << std::endl;
    }
};

int main() {
    MyClass obj1(5); // 유효한 생성자 호출
    // MyClass obj2 = 5; // 오류: 암묵적 변환 불가
    return 0;
}
```

위 예제에서 `obj1`은 유효하게 생성되지만, `obj2`는 암묵적 변환이 불가능하여 오류가 발생합니다.

## 설명
C++에서 암묵적 변환은 편리할 수 있지만, 잘못된 타입 변환이 발생할 가능성도 큽니다. 예를 들어, 다음과 같은 경우에 `explicit` 키워드를 사용하지 않으면 의도하지 않은 결과가 나올 수 있습니다:

```cpp
class MyClass {
public:
    MyClass(int value) {
        std::cout << "Value: " << value << std::endl;
    }
};

void function(MyClass obj) {
    // ...
}

int main() {
    function(10); // 암묵적 변환으로 MyClass 객체 생성
    return 0;
}
```

위 코드에서는 `function(10)` 호출 시 `MyClass`의 생성자가 암묵적으로 호출됩니다. 이를 방지하기 위해 `explicit` 키워드를 사용해야 합니다.

### 일반적인 함정
- `explicit` 키워드는 단일 인수 생성자에만 적용됩니다. 여러 인수를 가진 생성자에는 영향을 미치지 않습니다.
- 변환 연산자에 대해서도 `explicit`를 사용할 수 있지만, 일반적으로 사용 빈도가 낮습니다.

## 한 줄 요약
C++의 `explicit` 키워드는 생성자의 암묵적 호출을 방지하여 코드의 명확성과 안전성을 높이는 데 도움을 줍니다.