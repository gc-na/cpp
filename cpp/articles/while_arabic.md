<!--
Meta Description: # حلقة "while" في C++ ## ملخص حلقة "while" في C++ هي عبارة عن بنية تحكم تتيح تنفيذ مجموعة من التعليمات طالما أن الشرط المحدد صحيح. تُستخدم بشكل شائع ل...
Meta Keywords: while, حلقة, شرط, الشرط, صحيح
-->

# حلقة "while" في C++

## ملخص
حلقة "while" في C++ هي عبارة عن بنية تحكم تتيح تنفيذ مجموعة من التعليمات طالما أن الشرط المحدد صحيح. تُستخدم بشكل شائع لتكرار العمليات حتى يتحقق شرط معين.

## التوثيق
تُستخدم حلقة "while" في C++ لتنفيذ كود معين مرارًا وتكرارًا، بناءً على شرط منطقي. إذا كان الشرط صحيحًا، يتم تنفيذ الكود داخل الحلقة، وإلا يتم الخروج منها. التركيب العام لحلقة "while" هو كالتالي:

```cpp
while (condition) {
    // الكود الذي سيتم تنفيذه طالما أن الشرط صحيح
}
```

### الهدف
الهدف من حلقة "while" هو توفير وسيلة لتنفيذ كود عدة مرات بناءً على شرط محدد، مما يسمح بتنفيذ المهام المتكررة بشكل فعال.

### الاستخدام
تستخدم حلقة "while" في العديد من الحالات، مثل:
- معالجة البيانات حتى الوصول إلى نهاية مجموعة البيانات.
- تنفيذ العمليات حتى تحقق شرط معين.
- الانتظار حتى يتم تلقي مدخلات من المستخدم.

## الأمثلة
### مثال 1: حلقة بسيطة
```cpp
#include <iostream>
using namespace std;

int main() {
    int count = 0;
    while (count < 5) {
        cout << "العد: " << count << endl;
        count++;
    }
    return 0;
}
```

### مثال 2: حلقة مع شرط معقد
```cpp
#include <iostream>
using namespace std;

int main() {
    int number;
    cout << "أدخل عددًا (0 للخروج): ";
    cin >> number;
    
    while (number != 0) {
        cout << "أنت أدخلت: " << number << endl;
        cout << "أدخل عددًا آخر (0 للخروج): ";
        cin >> number;
    }
    
    cout << "تم إنهاء البرنامج." << endl;
    return 0;
}
```

## الشرح
### الأخطاء الشائعة
1. **الحلقة اللانهائية**: إذا كان شرط الحلقة دائمًا صحيحًا، ستدخل البرنامج في حلقة لانهائية، مما يؤدي إلى توقف البرنامج. لذا يجب التأكد من أن الشرط سيتغير في كل دورة.
2. **عدم تهيئة المتغيرات**: تأكد من تهيئة المتغيرات المستخدمة في الشرط قبل بدء حلقة "while"، لتفادي سلوك غير متوقع.

### ملاحظات إضافية
- يمكن استخدام حلقة "while" مع أي تعبير منطقي. إذا كان التعبير صحيحًا (true)، تستمر الحلقة في التنفيذ.
- يمكن أيضًا استخدام حلقة "do-while" التي تنفذ الكود مرة واحدة على الأقل حتى إذا كان الشرط خاطئًا في البداية.

## ملخص جملة واحدة
تعتبر حلقة "while" في C++ وسيلة فعالة لتنفيذ كود معين بشكل متكرر بناءً على شرط محدد.