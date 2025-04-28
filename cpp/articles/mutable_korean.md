<!--
Meta Description: # C++에서의 mutable 키워드: 용도와 사용법 ## 개요 C++에서 `mutable` 키워드는 클래스의 멤버 변수를 상수 객체 내에서도 수정할 수 있게 해주는 특수한 키워드입니다. 이를 통해 상수 객체의 상태를 변경하는 것이 가능하며, 주로 캐시와 같은 작업에서...
Meta Keywords: mutable, const, 변수를, 객체의, counter
-->

# C++에서의 mutable 키워드: 용도와 사용법

## 개요
C++에서 `mutable` 키워드는 클래스의 멤버 변수를 상수 객체 내에서도 수정할 수 있게 해주는 특수한 키워드입니다. 이를 통해 상수 객체의 상태를 변경하는 것이 가능하며, 주로 캐시와 같은 작업에서 유용하게 사용됩니다.

## 문서화

### 목적
`mutable` 키워드는 클래스의 멤버 변수를 상수(`const`)로 선언된 객체 내에서도 수정할 수 있도록 허용합니다. 이는 특히 객체가 상수일 때도 내부 상태를 변경해야 하는 경우 유용합니다.

### 사용법
`mutable` 키워드는 클래스 멤버 변수 선언 시 사용됩니다. 아래와 같은 형식으로 사용합니다:

```cpp
class ClassName {
public:
    mutable int mutableVar;
    void function() const {
        mutableVar = 10;  // const 함수 내에서 mutable 변수를 수정 가능
    }
};
```

### 세부사항
- `mutable` 멤버 변수는 오직 `const` 멤버 함수 내에서만 수정 가능하므로, 이를 활용하여 객체의 불변성(immutability)을 유지하면서도 내부 상태를 관리할 수 있습니다.
- 이 키워드는 주로 성능 최적화, 캐싱, 그리고 비즈니스 로직을 처리하기 위해 사용됩니다.
- `mutable`는 기본형, 포인터, 객체 등 다양한 타입의 멤버 변수에 적용할 수 있습니다.

## 예시

### 기본 사용 예
```cpp
#include <iostream>

class Example {
public:
    mutable int counter;

    Example() : counter(0) {}

    void increment() const {
        counter++;  // counter는 const 메서드 내에서 수정 가능
    }

    void display() const {
        std::cout << "Counter: " << counter << std::endl;
    }
};

int main() {
    const Example ex;
    ex.increment();  // const 객체에서 mutable 변수를 수정
    ex.display();    // 출력: Counter: 1
    return 0;
}
```

## 설명
- `mutable` 키워드를 사용할 때의 일반적인 함정은, `const` 객체가 아닌 경우에 이 키워드를 사용하는 것입니다. `mutable`는 `const` 멤버 함수 내에서만 의미가 있으며, 그렇지 않을 경우 일반적인 멤버 변수와 동일하게 동작합니다.
- `mutable` 변수를 사용하여 객체의 상태를 변경할 수 있지만, 이를 남용하면 객체의 불변성 원칙을 위반할 수 있으므로 주의해야 합니다.

## 한 줄 요약
C++에서 `mutable` 키워드는 상수 객체의 멤버 변수를 수정 가능하게 하여, 객체의 불변성을 유지하면서도 내부 상태를 관리할 수 있게 해준다.