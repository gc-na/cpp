<!--
Meta Description: # الصديق في C++ ## ملخص في لغة C++، تُستخدم الكلمة المفتاحية `friend` لتسمح لوظائف أو فئات معينة بالوصول إلى الأعضاء الخاصة (private) والفئات المحمية ...
Meta Keywords: classa, friend, إلى, classb, value
-->

# الصديق في C++

## ملخص
في لغة C++، تُستخدم الكلمة المفتاحية `friend` لتسمح لوظائف أو فئات معينة بالوصول إلى الأعضاء الخاصة (private) والفئات المحمية (protected) لفئة أخرى. تعتبر هذه الميزة مفيدة لتسهيل التفاعل بين الكائنات.

## الوثائق
كلمة `friend` تُستخدم لتحديد الصداقات بين الفئات أو الوظائف. عندما تُعلن وظيفة أو فئة كصديق (friend) لفئة أخرى، فإنها تستطيع الوصول إلى الأعضاء الخاصة والفئات المحمية لتلك الفئة. يُستخدم هذا المفهوم بشكل شائع لتعزيز التعاون بين الكائنات دون الحاجة إلى جعل جميع الأعضاء العامة.

### الاستخدام
```cpp
class ClassA; // Forward declaration

class ClassB {
public:
    void show(ClassA& a);
};

class ClassA {
private:
    int value;

public:
    ClassA(int v) : value(v) {}

    friend void ClassB::show(ClassA& a); // إعلان ClassB كصديق لـ ClassA
};

void ClassB::show(ClassA& a) {
    std::cout << "Value: " << a.value << std::endl; // الوصول إلى الأعضاء الخاصة
}
```

## الأمثلة
### مثال أساسي
```cpp
#include <iostream>

class Box {
private:
    int length;

public:
    Box(int l) : length(l) {}

    friend void printLength(Box b); // إعلان دالة كصديق
};

void printLength(Box b) {
    std::cout << "Length: " << b.length << std::endl; // الوصول إلى العضو الخاص
}

int main() {
    Box box(10);
    printLength(box); // إخراج: Length: 10
    return 0;
}
```

### مثال على الصداقة بين الفئات
```cpp
#include <iostream>

class ClassA;

class ClassB {
public:
    void show(ClassA& a);
};

class ClassA {
private:
    int value;

public:
    ClassA(int v) : value(v) {}

    friend void ClassB::show(ClassA& a); // إعلان ClassB كصديق
};

void ClassB::show(ClassA& a) {
    std::cout << "Value: " << a.value << std::endl; // الوصول إلى العضو الخاص
}

int main() {
    ClassA a(42);
    ClassB b;
    b.show(a); // إخراج: Value: 42
    return 0;
}
```

## الشرح
### الأخطاء الشائعة
- **استخدام الصداقة بشكل مفرط**: يمكن أن يؤدي استخدام `friend` بشكل مفرط إلى كود يصعب صيانته. يجب أن تُستخدم بعناية.
- **تجاوز حدود الوصول**: يجب أن يتم استخدام `friend` فقط عند الحاجة لتجنب التعقيد غير الضروري.

### ملاحظات إضافية
- يمكن أن تكون الفئات أو الوظائف صديقة لفئة واحدة أو أكثر.
- يمكن أن تكون الفئة نفسها صديقة لنفسها، مما يتيح لها الوصول إلى أعضائها الخاصة.

## ملخص جملة واحدة
تتيح الكلمة المفتاحية `friend` في C++ وظائف وفئات معينة الوصول إلى الأعضاء الخاصة لفئة أخرى، مما يسهل التعاون بين الكائنات.