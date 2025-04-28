<!--
Meta Description: # استخدام dynamic_cast في C++ ## ملخص `dynamic_cast` هو تعبير في C++ يُستخدم لتحويل المؤشرات أو المراجع بين الأنواع المتوارثة. يتيح هذا النوع من التحو...
Meta Keywords: derived, dynamic_cast, std, class, base
-->

# استخدام dynamic_cast في C++

## ملخص
`dynamic_cast` هو تعبير في C++ يُستخدم لتحويل المؤشرات أو المراجع بين الأنواع المتوارثة. يتيح هذا النوع من التحويل التأكد من سلامته في وقت التشغيل، مما يجعله أداة قوية عند التعامل مع وراثة متعددة المستويات.

## التوثيق
### الغرض
يستخدم `dynamic_cast` لتحويل المؤشرات أو المراجع إلى نوع مشتق من نوع أساسي. يوفر هذا التحويل أمانًا إضافيًا عن طريق التحقق مما إذا كان التحويل ممكنًا في وقت التشغيل. إذا لم يكن التحويل ممكنًا، فإن `dynamic_cast` يُرجع قيمة `nullptr` للمؤشرات، أو يُرمي استثناء من نوع `std::bad_cast` للمراجع.

### الاستخدام
يتطلب استخدام `dynamic_cast` أن يكون النوع الأساسي عبارة عن فئة تحتوي على على دالة افتراضية واحدة على الأقل. يتم استخدامه بشكل شائع في التطبيقات التي تستخدم الوراثة المتعددة.

#### الصيغة العامة:
```cpp
dynamic_cast<target_type>(expression)
```
- `target_type`: النوع الذي نرغب في تحويله إليه.
- `expression`: التعبير الذي يمثل كائنًا من النوع الأساسي.

## الأمثلة
### مثال 1: تحويل مؤشر
```cpp
#include <iostream>

class Base {
public:
    virtual ~Base() {}
};

class Derived : public Base {
public:
    void show() { std::cout << "Derived class" << std::endl; }
};

int main() {
    Base* b = new Derived();
    Derived* d = dynamic_cast<Derived*>(b);
    
    if (d) {
        d->show(); // سيتم طباعة "Derived class"
    } else {
        std::cout << "Conversion failed" << std::endl;
    }
    
    delete b;
    return 0;
}
```

### مثال 2: تحويل مرجع
```cpp
#include <iostream>

class Base {
public:
    virtual ~Base() {}
};

class Derived : public Base {
public:
    void show() { std::cout << "Derived class" << std::endl; }
};

int main() {
    Base* b = new Derived();
    
    try {
        Derived& d = dynamic_cast<Derived&>(*b);
        d.show(); // سيتم طباعة "Derived class"
    } catch (std::bad_cast&) {
        std::cout << "Conversion failed" << std::endl;
    }
    
    delete b;
    return 0;
}
```

## الشرح
### الأخطاء الشائعة
- **عدم وجود دالة افتراضية**: إذا كانت الفئة الأساسية لا تحتوي على دالة افتراضية، فإن `dynamic_cast` لن يعمل.
- **تحويل غير ممكن**: إذا حاولت تحويل كائن لا ينتمي إلى النوع المستهدف، فسيؤدي ذلك إلى إرجاع `nullptr` للمؤشرات أو إلقاء استثناء `std::bad_cast` للمراجع.
- **الأداء**: نظرًا لأن `dynamic_cast` يتحقق من صحة النوع في وقت التشغيل، فإنه قد يكون أبطأ من التحويلات الأخرى مثل `static_cast` أو `reinterpret_cast`.

## ملخص جملة واحدة
`dynamic_cast` هو تعبير في C++ يُستخدم لتحويل المؤشرات أو المراجع بين الأنواع المتوارثة مع التحقق من سلامة التحويل في وقت التشغيل.