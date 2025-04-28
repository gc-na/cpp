<!--
Meta Description: # C++에서 typeid 사용법: 타입 식별의 모든 것 ## 요약 C++의 `typeid` 연산자는 변수나 객체의 타입 정보를 런타임에 확인할 수 있는 기능을 제공합니다. 이는 주로 다형성(polymorphism)과 관련된 코드에서 유용하게 활용됩니다. ## 문서화 ...
Meta Keywords: typeid, 있습니다, 객체의, 정보를, 확인할
-->

# C++에서 typeid 사용법: 타입 식별의 모든 것

## 요약
C++의 `typeid` 연산자는 변수나 객체의 타입 정보를 런타임에 확인할 수 있는 기능을 제공합니다. 이는 주로 다형성(polymorphism)과 관련된 코드에서 유용하게 활용됩니다.

## 문서화
`typeid`는 C++ 표준 라이브러리의 RTTI(런타임 타입 정보) 기능의 일환으로, 객체의 실제 타입을 판별하기 위해 사용됩니다. 이 연산자는 다음과 같은 목적으로 사용됩니다:

- **타입 정보 확인**: 객체의 실제 타입을 확인할 수 있습니다.
- **다형성 처리**: 상속 구조에서 객체의 타입을 확인하여 올바른 동작을 수행할 수 있습니다.

### 사용법
`typeid` 연산자는 다음과 같은 형태로 사용됩니다:

```cpp
typeid(expression)
```

여기서 `expression`은 타입 정보를 확인하려는 변수나 객체입니다. 반환 값은 `std::type_info` 객체로, 이 객체를 통해 타입 이름 등의 정보를 얻을 수 있습니다.

### 예시
```cpp
#include <iostream>
#include <typeinfo>

class Base {};
class Derived : public Base {};

int main() {
    Base* b = new Derived();

    // typeid를 사용하여 타입 확인
    std::cout << "b의 타입: " << typeid(*b).name() << std::endl; // Derived의 타입 출력

    delete b;
    return 0;
}
```

위의 코드에서 `typeid`를 사용하여 `Base` 포인터가 가리키는 객체의 실제 타입인 `Derived`를 확인할 수 있습니다.

## 설명
`typeid`를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **다형성 객체**: `typeid`를 사용할 때, 반드시 객체를 역참조(dereference)하여 실제 타입을 확인해야 합니다. 단순히 포인터에 대해 `typeid`를 사용하면 포인터의 타입 정보만을 반환합니다.
- **RTTI 비활성화**: `typeid`는 RTTI(런타임 타입 정보)가 활성화된 경우에만 작동합니다. 컴파일러 설정에 따라 RTTI가 비활성화될 수 있으므로, 이 경우 `typeid`는 예상치 못한 결과를 반환할 수 있습니다.
- **리턴 타입**: `typeid`의 반환 값은 `std::type_info` 객체입니다. 이 객체는 `name()` 메서드를 통해 타입 이름을 문자열 형태로 반환할 수 있습니다.

## 한 줄 요약
C++에서 `typeid`는 객체의 실제 타입 정보를 런타임에 확인할 수 있는 유용한 연산자입니다.