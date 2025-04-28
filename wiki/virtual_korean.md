<!--
Meta Description: # C++의 가상 함수(virtual) - 객체 지향 프로그래밍의 핵심 ## 개요 C++의 `virtual` 키워드는 다형성을 구현하는 데 중요한 역할을 합니다. 이를 통해 기본 클래스에서 정의된 함수가 파생 클래스에서 재정의될 수 있도록 하여 런타임에 적절한 함수가 ...
Meta Keywords: virtual, show, class, base, std
-->

# C++의 가상 함수(virtual) - 객체 지향 프로그래밍의 핵심

## 개요
C++의 `virtual` 키워드는 다형성을 구현하는 데 중요한 역할을 합니다. 이를 통해 기본 클래스에서 정의된 함수가 파생 클래스에서 재정의될 수 있도록 하여 런타임에 적절한 함수가 호출되도록 합니다.

## 문서화
### 목적
`virtual` 키워드는 객체 지향 프로그래밍에서 다형성을 지원합니다. 이는 동일한 인터페이스를 가진 여러 클래스에서 서로 다른 동작을 구현할 수 있게 해주며, 프로그램의 유연성과 확장성을 높여줍니다.

### 사용법
`virtual` 키워드는 함수 선언 앞에 붙여 사용합니다. 기본 클래스에서 `virtual` 함수를 선언하면, 이 함수를 파생 클래스에서 재정의할 수 있습니다. 호출 시, 객체의 실제 타입에 따라 적절한 함수가 실행됩니다.

#### 기본 문법
```cpp
class Base {
public:
    virtual void show() {
        std::cout << "Base class show function called." << std::endl;
    }
};

class Derived : public Base {
public:
    void show() override { // C++11부터 'override' 키워드 사용 권장
        std::cout << "Derived class show function called." << std::endl;
    }
};
```

## 예제
다음은 `virtual` 키워드를 사용한 간단한 예제입니다.

```cpp
#include <iostream>

class Base {
public:
    virtual void show() {
        std::cout << "Base class show function called." << std::endl;
    }
    virtual ~Base() {} // 가상 소멸자
};

class Derived : public Base {
public:
    void show() override {
        std::cout << "Derived class show function called." << std::endl;
    }
};

int main() {
    Base* basePtr;
    Derived derivedObj;
    basePtr = &derivedObj;

    // 실제 객체의 타입에 따라 적절한 show() 호출
    basePtr->show(); // "Derived class show function called." 출력

    return 0;
}
```

## 설명
- **가상 소멸자**: 기본 클래스에 가상 소멸자를 추가하는 것이 일반적으로 권장됩니다. 이는 파생 클래스의 객체가 삭제될 때, 파생 클래스의 소멸자가 올바르게 호출되도록 보장합니다.
- **성능**: `virtual` 함수를 사용할 경우, 컴파일 타임에 함수 호출이 결정되지 않고 런타임에 결정되므로 성능에 약간의 오버헤드가 발생할 수 있습니다.
- **순환 참조**: 가상 함수와 관련된 순환 참조를 피해야 하며, 이를 위해 스마트 포인터를 사용하는 것이 좋습니다.

## 한줄 요약
C++의 `virtual` 키워드는 다형성을 지원하며, 기본 클래스의 함수를 파생 클래스에서 재정의할 수 있게 해주는 핵심 기능입니다.