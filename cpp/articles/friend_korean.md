<!--
Meta Description: # C++에서의 friend: 접근 제어와 클래스 간의 관계 ## 개요 C++의 `friend` 키워드는 클래스 간의 접근 제어를 허용하여 특정 함수나 다른 클래스가 해당 클래스의 private 및 protected 멤버에 접근할 수 있도록 하는 기능입니다. 이를 통해...
Meta Keywords: friend, 클래스의, int, 클래스, 함수나
-->

# C++에서의 friend: 접근 제어와 클래스 간의 관계

## 개요
C++의 `friend` 키워드는 클래스 간의 접근 제어를 허용하여 특정 함수나 다른 클래스가 해당 클래스의 private 및 protected 멤버에 접근할 수 있도록 하는 기능입니다. 이를 통해 캡슐화 원칙을 유지하면서도 필요한 경우에 한해 유연한 접근을 제공합니다.

## 문서화
### 목적
`friend` 키워드의 주 목적은 클래스의 내부 구현을 보호하면서도 특정 함수나 클래스가 해당 클래스의 비공식적인 내부 인터페이스에 접근할 수 있게 하는 것입니다. 이는 복잡한 데이터 구조를 다룰 때 유용하며, 두 클래스 간의 협력을 가능하게 합니다.

### 사용법
`friend` 키워드는 클래스 정의 내에서 특정 함수나 클래스의 이름 앞에 선언됩니다. 이를 통해 해당 함수나 클래스가 그 클래스의 private 및 protected 멤버에 접근할 수 있습니다.

```cpp
class MyClass {
private:
    int data;

public:
    MyClass(int value) : data(value) {}

    // friend 함수 선언
    friend void showData(MyClass& obj);
};

// friend 함수 정의
void showData(MyClass& obj) {
    std::cout << "Data: " << obj.data << std::endl;
}
```

### 상세 설명
- `friend`는 클래스의 비공식적인 접근을 허용하지만, 캡슐화 원칙을 무너뜨릴 수 있으므로 신중하게 사용해야 합니다.
- 여러 클래스나 함수를 동시에 friend로 지정할 수 있으며, friend 선언은 클래스 내부에 위치해야 합니다.
- `friend` 선언은 클래스의 멤버가 아니므로 해당 클래스의 객체 없이도 호출 가능합니다.

## 예제
### 기본 사용 예제
```cpp
#include <iostream>

class Box {
private:
    int length;

public:
    Box(int l) : length(l) {}

    // friend 함수 선언
    friend void printLength(Box& b);
};

// friend 함수 정의
void printLength(Box& b) {
    std::cout << "Length: " << b.length << std::endl;
}

int main() {
    Box b(10);
    printLength(b); // Length: 10
    return 0;
}
```

### 클래스 간의 friend 예제
```cpp
#include <iostream>

class ClassB; // 전방 선언

class ClassA {
public:
    void showB(ClassB& b);
};

class ClassB {
private:
    int value;

public:
    ClassB(int v) : value(v) {}

    friend void ClassA::showB(ClassB& b);
};

void ClassA::showB(ClassB& b) {
    std::cout << "Value: " << b.value << std::endl;
}

int main() {
    ClassB b(20);
    ClassA a;
    a.showB(b); // Value: 20
    return 0;
}
```

## 설명
- `friend` 키워드를 남용하면 코드의 유지보수성이 떨어질 수 있으며, 클래스 간의 의존성이 증가할 수 있습니다. 따라서 코드 설계 시 신중하게 고려해야 합니다.
- `friend`는 상속받은 클래스에서 원래 클래스의 private 멤버에 접근할 수 있는 권한을 자동으로 부여하지 않습니다.
- `friend` 선언은 함수나 클래스의 접근을 허용하는 것일 뿐, 해당 함수나 클래스가 호출될 때의 접근 권한을 결정하지 않으므로 혼란을 피하기 위해 명확한 설계가 필요합니다.

## 한 줄 요약
C++의 `friend` 키워드는 클래스의 private 및 protected 멤버에 특정 함수나 클래스가 접근할 수 있도록 허용하는 기능입니다.