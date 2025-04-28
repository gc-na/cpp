<!--
Meta Description: # C++의 "private" 접근 지정자 ## 개요 C++에서 "private"는 클래스의 멤버 변수를 외부에서 접근할 수 없도록 제한하는 접근 지정자입니다. 이 키워드는 객체 지향 프로그래밍의 캡슐화 원칙을 지원하여 데이터 보호 및 코드 유지보수를 용이하게 합니다....
Meta Keywords: private, 클래스의, 접근할, 외부에서, 데이터
-->

# C++의 "private" 접근 지정자

## 개요
C++에서 "private"는 클래스의 멤버 변수를 외부에서 접근할 수 없도록 제한하는 접근 지정자입니다. 이 키워드는 객체 지향 프로그래밍의 캡슐화 원칙을 지원하여 데이터 보호 및 코드 유지보수를 용이하게 합니다.

## 문서화
"private" 접근 지정자는 클래스 내에서 선언된 멤버 변수나 함수가 클래스 외부에서 접근할 수 없도록 합니다. 이는 객체의 내부 상태를 보호하고, 클래스의 인터페이스를 명확하게 정의하는 데 중요한 역할을 합니다. 

### 용도
- **데이터 보호**: 클래스의 내부 데이터를 외부에서 직접 수정할 수 없도록 하여, 데이터 무결성을 유지합니다.
- **캡슐화**: 클래스의 구현 세부 사항을 숨김으로써, 코드의 변경이 외부에 미치는 영향을 최소화합니다.
- **인터페이스 정의**: 클래스의 퍼블릭 API를 명확하게 하고, 사용자에게 필요한 기능만을 제공합니다.

### 사용법
"private" 키워드는 클래스 정의 내에서 사용됩니다. 다음과 같은 형식으로 사용됩니다:

```cpp
class ClassName {
private:
    int privateVariable; // private 변수
    void privateMethod(); // private 메서드

public:
    void publicMethod(); // public 메서드
};
```

## 예제
아래는 "private" 접근 지정자를 사용하는 간단한 예제입니다.

```cpp
#include <iostream>
using namespace std;

class Example {
private:
    int secretNumber; // private 변수

public:
    Example(int num) : secretNumber(num) {} // 생성자

    void showSecret() {
        cout << "The secret number is: " << secretNumber << endl;
    }
};

int main() {
    Example ex(42);
    ex.showSecret(); // "The secret number is: 42" 출력
    // ex.secretNumber = 100; // 오류: 'secretNumber'는 private입니다.
    return 0;
}
```

## 설명
"private" 접근 지정자를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **접근 제한**: 클래스 내부에서만 접근할 수 있으므로, 외부에서는 해당 멤버에 직접 접근할 수 없습니다. 이는 의도하지 않은 데이터 변경을 방지합니다.
- **상속 문제**: 자식 클래스에서는 부모 클래스의 private 멤버에 접근할 수 없습니다. 필요한 경우 protected 접근 지정자를 사용하는 것을 고려해야 합니다.
- **디버깅의 어려움**: private 멤버는 외부에서 직접 확인할 수 없기 때문에, 디버깅 시 추가적인 방법이 필요할 수 있습니다.

## 한 줄 요약
C++의 "private" 접근 지정자는 클래스의 멤버를 외부에서 접근할 수 없도록 제한하여 데이터 보호 및 캡슐화를 지원합니다.