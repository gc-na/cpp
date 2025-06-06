<!--
Meta Description: # C++ 클래스: 객체 지향 프로그래밍의 기본 ## 개요 C++에서 클래스는 객체 지향 프로그래밍(OOP)의 핵심 개념으로, 데이터와 그 데이터를 처리하는 함수를 하나의 단위로 묶는 사용자 정의 데이터 타입입니다. 클래스는 객체를 생성하는 템플릿 역할을 하며, 코드의...
Meta Keywords: int, 클래스는, 데이터, 있습니다, 클래스를
-->

# C++ 클래스: 객체 지향 프로그래밍의 기본

## 개요
C++에서 클래스는 객체 지향 프로그래밍(OOP)의 핵심 개념으로, 데이터와 그 데이터를 처리하는 함수를 하나의 단위로 묶는 사용자 정의 데이터 타입입니다. 클래스는 객체를 생성하는 템플릿 역할을 하며, 코드의 재사용성과 구조화된 설계를 가능하게 합니다.

## 문서화
클래스는 C++에서 객체 지향 프로그래밍의 중심으로 작용합니다. 클래스는 다음과 같은 요소를 포함할 수 있습니다:

- **속성(Attributes)**: 클래스가 보유하는 데이터 멤버입니다.
- **메서드(Methods)**: 클래스에 정의된 함수로, 객체의 행동을 정의합니다.

### 사용법
클래스를 정의하고 사용하는 기본적인 구문은 다음과 같습니다:

```cpp
class ClassName {
public:
    // 데이터 멤버
    int attribute;

    // 생성자
    ClassName(int value) {
        attribute = value;
    }

    // 메서드
    void display() {
        std::cout << "Attribute: " << attribute << std::endl;
    }
};
```

위의 예시에서 `ClassName`이라는 클래스를 정의하였고, `attribute`라는 정수형 속성과 `display`라는 메서드를 포함하고 있습니다.

클래스를 사용하여 객체를 생성하는 방법은 다음과 같습니다:

```cpp
int main() {
    ClassName obj(10); // 객체 생성
    obj.display();     // 메서드 호출
    return 0;
}
```

## 예제
여기 간단한 클래스 사용 예제를 제시합니다.

```cpp
#include <iostream>

class Rectangle {
public:
    int width, height;

    Rectangle(int w, int h) {
        width = w;
        height = h;
    }

    int area() {
        return width * height;
    }
};

int main() {
    Rectangle rect(5, 3);
    std::cout << "Area: " << rect.area() << std::endl; // 결과: Area: 15
    return 0;
}
```

이 예제에서는 `Rectangle` 클래스를 정의하고, `area` 메서드를 통해 면적을 계산합니다.

## 설명
클래스를 사용할 때 주의해야 할 몇 가지 사항은 다음과 같습니다:

1. **접근 제어자**: 클래스의 데이터 멤버는 기본적으로 `private`입니다. 이를 `public`으로 설정하여 외부에서 접근할 수 있도록 해야 합니다. 접근 제어자를 적절히 사용하지 않으면 데이터 은닉의 이점을 잃을 수 있습니다.

2. **생성자와 소멸자**: 클래스는 객체가 생성될 때 호출되는 생성자와, 객체가 소멸될 때 호출되는 소멸자를 가질 수 있습니다. 메모리 관리에 있어 이 두 가지를 올바르게 사용하는 것이 중요합니다.

3. **상속**: 클래스는 다른 클래스로부터 상속받을 수 있습니다. 이는 코드의 재사용성을 높이고, 다형성을 구현하는 데 유용합니다.

4. **복사 생성자**: 객체가 복사될 때 호출되는 복사 생성자를 정의하지 않으면 컴파일러가 기본 복사 생성자를 생성합니다. 이는 깊은 복사(deep copy)와 얕은 복사(shallow copy) 문제를 일으킬 수 있습니다.

## 한 줄 요약
C++의 클래스는 데이터와 메서드를 결합하여 객체 지향 프로그래밍을 지원하는 사용자 정의 데이터 타입입니다.