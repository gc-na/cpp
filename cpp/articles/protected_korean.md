<!--
Meta Description: # C++의 protected 접근 제어자: 이해와 활용 ## 개요 C++에서 `protected`는 클래스의 멤버 변수를 보호하는 접근 제어자입니다. 이 접근 제어자는 클래스와 해당 클래스를 상속받은 자식 클래스에서만 접근할 수 있는 멤버를 정의할 때 사용됩니다. #...
Meta Keywords: protected, 접근할, 멤버를, 클래스, 클래스에서
-->

# C++의 protected 접근 제어자: 이해와 활용

## 개요
C++에서 `protected`는 클래스의 멤버 변수를 보호하는 접근 제어자입니다. 이 접근 제어자는 클래스와 해당 클래스를 상속받은 자식 클래스에서만 접근할 수 있는 멤버를 정의할 때 사용됩니다.

## 문서화
`protected` 접근 제어자는 C++의 클래스 내에서 멤버 변수와 메서드에 대한 접근을 제한하는데 사용됩니다. `protected`로 선언된 멤버는 다음과 같은 특징을 가집니다:

- **클래스 내 접근**: 해당 멤버는 선언된 클래스 내에서 자유롭게 접근할 수 있습니다.
- **상속된 클래스에서 접근**: `protected` 멤버는 자식 클래스에서 접근할 수 있으므로, 상속 관계에 있는 클래스 간에 멤버를 공유할 수 있습니다.
- **외부 클래스에서 접근 불가**: `protected` 멤버는 해당 클래스를 상속하지 않은 외부 클래스에서는 접근할 수 없습니다.

### 사용 예
`protected` 접근 제어자는 다음과 같은 상황에서 유용하게 사용됩니다:
- 클래스의 내부 구현을 숨기면서도 자식 클래스에서 해당 멤버를 사용할 수 있도록 해야 할 경우.
- 클래스 계층 구조에서 동작을 공유하고자 할 때.

## 예제
다음은 `protected` 멤버를 사용하는 간단한 예제입니다:

```cpp
#include <iostream>

class Base {
protected:
    int protectedVar;

public:
    Base() : protectedVar(10) {}
};

class Derived : public Base {
public:
    void showVar() {
        std::cout << "Protected Variable: " << protectedVar << std::endl;
    }
};

int main() {
    Derived d;
    d.showVar(); // Protected Variable: 10
    return 0;
}
```

위의 예제에서 `Base` 클래스의 `protectedVar`는 `Derived` 클래스에서 접근 가능하지만, `main` 함수에서는 직접 접근할 수 없습니다.

## 설명
`protected` 접근 제어자를 사용할 때 주의해야 할 점은 다음과 같습니다:

- **상속 관계 이해**: 자식 클래스에서만 접근할 수 있으므로, 상속 구조를 잘 이해하고 사용해야 합니다.
- **혼동 방지**: `private`와 `protected`의 차이를 명확히 인지해야 합니다. `private`는 자식 클래스에서도 접근할 수 없습니다.
- **설계 고려**: `protected` 멤버를 너무 많이 사용하면 상속을 통한 의존성이 높아질 수 있으므로, 필요한 경우에만 사용해야 합니다.

## 한 줄 요약
C++의 `protected` 접근 제어자는 클래스와 자식 클래스에서만 접근 가능한 멤버를 정의하는 데 사용됩니다.