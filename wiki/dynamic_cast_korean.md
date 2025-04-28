<!--
Meta Description: # C++의 dynamic_cast: 다형성을 위한 안전한 형 변환 ## 개요 C++에서 `dynamic_cast`는 런타임에 객체의 형을 안전하게 변환하기 위해 사용되는 연산자입니다. 주로 다형성이 필요한 경우, 특히 상속 관계에 있는 클래스 간의 형 변환에서 유용합...
Meta Keywords: dynamic_cast, base, derived, std, 클래스
-->

# C++의 dynamic_cast: 다형성을 위한 안전한 형 변환

## 개요
C++에서 `dynamic_cast`는 런타임에 객체의 형을 안전하게 변환하기 위해 사용되는 연산자입니다. 주로 다형성이 필요한 경우, 특히 상속 관계에 있는 클래스 간의 형 변환에서 유용합니다. `dynamic_cast`는 타입 안전성을 보장하며, 변환이 실패할 경우 nullptr을 반환합니다.

## 문서화

### 목적
`dynamic_cast`는 상속 관계에 있는 클래스의 포인터나 참조를 안전하게 변환하기 위해 사용됩니다. 주로 베이스 클래스 포인터를 파생 클래스 포인터로 변환할 때 사용되며, 변환이 실패할 경우 nullptr을 반환하여 오류를 방지합니다.

### 사용법
`dynamic_cast`의 기본 구문은 다음과 같습니다:

```cpp
dynamic_cast<타입>(객체);
```

- **타입**: 변환하고자 하는 파생 클래스의 타입.
- **객체**: 변환하고자 하는 베이스 클래스의 포인터 또는 참조.

### 세부사항
- `dynamic_cast`는 반드시 RTTI(런타임 타입 정보)를 필요로 하며, RTTI는 `virtual` 키워드를 사용하여 정의된 클래스에서만 사용할 수 있습니다.
- 변환이 성공하면 지정한 타입의 포인터 또는 참조가 반환되며, 실패 시 nullptr을 반환합니다.
- `dynamic_cast`는 다형적 타입에만 적용 가능하며, 기본 타입(int, float 등)에는 사용할 수 없습니다.

## 예제

### 기본 사용 예제

```cpp
#include <iostream>

class Base {
public:
    virtual ~Base() {} // RTTI를 위한 가상 소멸자
};

class Derived : public Base {};

int main() {
    Base* b = new Derived(); // Base 클래스 포인터로 Derived 클래스 객체 생성
    Derived* d = dynamic_cast<Derived*>(b); // 안전한 형 변환

    if (d) {
        std::cout << "형 변환 성공!" << std::endl;
    } else {
        std::cout << "형 변환 실패!" << std::endl;
    }

    delete b;
    return 0;
}
```

### 변환 실패 예제

```cpp
#include <iostream>

class Base {
public:
    virtual ~Base() {}
};

class Derived : public Base {};

class AnotherClass {};

int main() {
    Base* b = new Base();
    Derived* d = dynamic_cast<Derived*>(b); // 형 변환 실패

    if (d) {
        std::cout << "형 변환 성공!" << std::endl;
    } else {
        std::cout << "형 변환 실패!" << std::endl; // 이 경우 출력됨
    }

    delete b;
    return 0;
}
```

## 설명
`dynamic_cast`를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **RTTI 필요성**: `dynamic_cast`는 RTTI에 의존하므로, 변환하려는 클래스는 가상 함수가 있어야 합니다. 그렇지 않으면 컴파일 타임 에러가 발생합니다.
- **null 체크**: 변환이 실패할 경우 nullptr을 반환하므로, 항상 null 체크를 수행해야 합니다. 
- **성능**: `dynamic_cast`는 런타임에 타입을 확인하므로, 성능에 영향을 줄 수 있습니다. 자주 호출되는 코드에서는 성능 저하를 유의해야 합니다.

## 한 줄 요약
`dynamic_cast`는 C++에서 상속 관계에 있는 클래스 간의 안전한 형 변환을 제공하는 연산자입니다.