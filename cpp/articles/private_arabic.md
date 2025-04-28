<!--
Meta Description: # كلمة "خاص" في لغة C++ ## ملخص تُستخدم الكلمة المحجوزة "private" في لغة C++ لتحديد مستوى الوصول إلى الأعضاء (المتغيرات والدوال) داخل الفئات (classes)...
Meta Keywords: private, الوصول, الأعضاء, إلى, يمكن
-->

# كلمة "خاص" في لغة C++

## ملخص
تُستخدم الكلمة المحجوزة "private" في لغة C++ لتحديد مستوى الوصول إلى الأعضاء (المتغيرات والدوال) داخل الفئات (classes). الأعضاء المُعلنة كـ "private" لا يمكن الوصول إليها إلا من خلال الدوال الأعضاء في نفس الفئة، مما يساهم في تحقيق الت encapsulation.

## الوثائق
تعتبر "private" واحدة من ثلاثة مستويات وصول في C++، إلى جانب "public" و"protected". عندما يتم تعريف عضو في فئة كـ "private"، فإنه يصبح غير متاح للوصول المباشر من خارج هذه الفئة. هذا يعزز من أمان البيانات ويقلل من الأخطاء الناتجة عن الوصول غير المصرح به.

### الاستخدام
لإعلان عضو كـ "private"، يتم استخدام الكلمة المحجوزة "private" قبل الأعضاء المراد حمايتهم. يُفضل استخدام "private" لتحسين التصميم البرمجي وفرض القواعد على كيفية استخدام الأعضاء.

### التفاصيل
- **الحماية:** تمنع الوصول غير المصرح به للأعضاء.
- **التحكم:** توفر تحكماً أفضل في كيفية استخدام الأعضاء.
- **الوراثة:** في الفئات المشتقة، لا يمكن الوصول إلى الأعضاء "private" من الفئة الأصلية.

## أمثلة

### المثال 1: استخدام "private" في فئة بسيطة
```cpp
#include <iostream>
using namespace std;

class MyClass {
private:
    int secretNumber;

public:
    MyClass(int num) : secretNumber(num) {}

    void showSecret() {
        cout << "The secret number is: " << secretNumber << endl;
    }
};

int main() {
    MyClass obj(42);
    obj.showSecret(); // يمكن الوصول إلى الدالة العامة
    // cout << obj.secretNumber; // خطأ: لا يمكن الوصول إلى secretNumber
    return 0;
}
```

### المثال 2: التأكد من حماية البيانات
```cpp
#include <iostream>
using namespace std;

class BankAccount {
private:
    double balance;

public:
    BankAccount() : balance(0.0) {}

    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    double getBalance() {
        return balance;
    }
};

int main() {
    BankAccount account;
    account.deposit(100);
    cout << "Current balance: " << account.getBalance() << endl; // 100
    // account.balance += 50; // خطأ: لا يمكن الوصول إلى balance
    return 0;
}
```

## الشرح
هناك بعض النقاط التي يجب مراعاتها عند استخدام "private":
- **الوصول غير المصرح به:** تأكد من عدم محاولة الوصول إلى الأعضاء "private" من خارج الفئة، حيث سيؤدي ذلك إلى أخطاء في الترجمة.
- **تطبيق جيد للـ encapsulation:** استخدام "private" بشكل مناسب يمكن أن يحسن من تنظيم الكود ويساعد في صيانته.
- **الوراثة:** تذكر أن الأعضاء "private" لا يمكن الوصول إليها من الفئات المشتقة، مما قد يكون مفيدًا أو غير مرغوب فيه حسب تصميم البرنامج.

## ملخص من جملة واحدة
تُستخدم الكلمة المحجوزة "private" في C++ لتحديد الأعضاء التي لا يمكن الوصول إليها إلا من داخل الفئة نفسها، مما يعزز من أمان البيانات وتنظيم الكود.