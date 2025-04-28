<!--
Meta Description: # C++의 struct: 구조체에 대한 모든 것 ## 개요 C++에서 `struct`는 관련 데이터를 그룹화하여 사용자 정의 데이터 형식을 만드는 데 사용되는 중요한 기능입니다. `struct`는 클래스와 유사하지만, 기본적으로 멤버의 접근 제어가 다르며, 간단한 데...
Meta Keywords: struct, int, 데이터, point, 기본적으로
-->

# C++의 struct: 구조체에 대한 모든 것

## 개요
C++에서 `struct`는 관련 데이터를 그룹화하여 사용자 정의 데이터 형식을 만드는 데 사용되는 중요한 기능입니다. `struct`는 클래스와 유사하지만, 기본적으로 멤버의 접근 제어가 다르며, 간단한 데이터 구조를 정의할 때 유용합니다.

## 문서화

### 목적
`struct`는 서로 관련된 데이터를 한 단위로 묶어 더 복잡한 데이터 유형을 만드는 데 사용됩니다. 이를 통해 코드의 가독성을 높이고, 데이터 관리 및 전달을 용이하게 합니다.

### 사용법
C++에서 `struct`를 사용하려면 다음과 같은 기본 구조를 따릅니다:

```cpp
struct StructName {
    // 멤버 변수
    DataType memberVariable1;
    DataType memberVariable2;
    
    // 멤버 함수
    void memberFunction() {
        // 함수 내용
    }
};
```

#### 멤버 접근 제어
`struct`의 멤버는 기본적으로 `public`으로 선언되며, 이는 외부에서 직접 접근할 수 있음을 의미합니다. 하지만 `class`와 마찬가지로 `private` 및 `protected` 접근 제어자를 사용할 수 있습니다.

### 세부사항
- **초기화**: `struct`의 인스턴스를 생성할 때 초기값을 설정할 수 있습니다.
- **메모리**: `struct`는 멤버 변수의 크기만큼 메모리를 차지합니다.
- **상속**: `struct`는 클래스와 동일하게 상속을 지원합니다. 다만 기본 접근 제어가 다르기 때문에 주의해야 합니다.

## 예제

### 기본 사용 예
```cpp
#include <iostream>
using namespace std;

struct Point {
    int x;
    int y;
};

int main() {
    Point p1; // Point 구조체의 인스턴스 생성
    p1.x = 10; // 멤버 변수에 값 할당
    p1.y = 20;

    cout << "Point p1: (" << p1.x << ", " << p1.y << ")" << endl; // 출력: Point p1: (10, 20)
    return 0;
}
```

### 함수와의 결합 예
```cpp
#include <iostream>
using namespace std;

struct Rectangle {
    int width;
    int height;

    int area() { // 멤버 함수
        return width * height;
    }
};

int main() {
    Rectangle rect;
    rect.width = 5;
    rect.height = 10;

    cout << "Rectangle area: " << rect.area() << endl; // 출력: Rectangle area: 50
    return 0;
}
```

## 설명
- **기본값**: `struct`의 멤버는 기본적으로 0으로 초기화되지 않으므로, 명시적으로 초기화해 주어야 합니다.
- **상속**: `struct`를 상속할 때는 기본 접근 제어가 `public`으로 설정되어 있으므로, 상속받은 멤버의 접근성에 유의해야 합니다.
- **복사**: `struct`는 기본적으로 얕은 복사를 수행합니다. 따라서 포인터 멤버가 있을 경우 주의가 필요합니다.

## 한 줄 요약
C++의 `struct`는 관련 데이터를 그룹화하여 복잡한 데이터 구조를 쉽게 정의하고 사용할 수 있도록 해주는 강력한 도구입니다.