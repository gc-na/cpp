<!--
Meta Description: # استخدام "thread_local" في C++ ## ملخص تُستخدم كلمة "thread_local" في C++ لتعريف متغيرات محلية خاصة بكل خيط (Thread)، مما يسمح لكل خيط بالاحتفاظ بنسخ...
Meta Keywords: thread_local, std, thread, خيط, الاستخدام
-->

# استخدام "thread_local" في C++

## ملخص
تُستخدم كلمة "thread_local" في C++ لتعريف متغيرات محلية خاصة بكل خيط (Thread)، مما يسمح لكل خيط بالاحتفاظ بنسخة مستقلة من المتغير دون التأثير على الخيوط الأخرى.

## الوثائق
### الغرض
تساعد "thread_local" في إنشاء متغيرات تكون خاصة بكل خيط، مما يعني أن كل خيط يمكن أن يتعامل مع نسخته الخاصة من المتغير دون تعارض مع الخيوط الأخرى. هذا مفيد في البرمجة المتزامنة حيث يمكن أن تؤدي المتغيرات المشتركة إلى مشاكل تتعلق بالتزامن.

### الاستخدام
يتم استخدام "thread_local" عن طريق إضافة الكلمة الرئيسية قبل تعريف المتغير. يمكن استخدامه مع أنواع البيانات الأساسية أو الكائنات.

#### صيغة الاستخدام:
```cpp
thread_local نوع_المتغير اسم_المتغير;
```

### التفاصيل
- **المدى**: يتم تهيئة المتغيرات المعلمة بـ "thread_local" عند الدخول إلى الخيط، وتبقى في الذاكرة حتى ينتهي الخيط.
- **التوافق**: تدعم كافة المترجمات الحديثة لـ C++ (C++11 وما بعدها).
- **الأداء**: قد تؤثر على الأداء بسبب تخصيص الذاكرة بشكل منفصل لكل خيط، لذا يُفضل استخدامه بحذر.

## أمثلة
### مثال 1: استخدام متغير عداد
```cpp
#include <iostream>
#include <thread>

thread_local int counter = 0;

void incrementCounter() {
    ++counter;
    std::cout << "Counter: " << counter << " in thread " << std::this_thread::get_id() << std::endl;
}

int main() {
    std::thread t1(incrementCounter);
    std::thread t2(incrementCounter);
    
    t1.join();
    t2.join();
    
    return 0;
}
```

### مثال 2: الاستخدام مع كائنات
```cpp
#include <iostream>
#include <thread>
#include <string>

thread_local std::string threadLocalString = "Hello from thread ";

void printThreadMessage() {
    std::cout << threadLocalString << std::this_thread::get_id() << std::endl;
}

int main() {
    std::thread t1(printThreadMessage);
    std::thread t2(printThreadMessage);
    
    t1.join();
    t2.join();
    
    return 0;
}
```

## الشرح
### الأخطاء الشائعة
- **عدم تهيئة المتغير**: يجب التأكد من أن المتغيرات التي تم تعريفها باستخدام "thread_local" تم تهيئتها بشكل صحيح.
- **الاستخدام المفرط**: يمكن أن يؤدي الاستخدام المفرط لـ "thread_local" إلى استهلاك الذاكرة بشكل زائد، خاصة في التطبيقات التي تحتوي على عدد كبير من الخيوط.
- **عدم الانتباه إلى التزامن**: على الرغم من أن المتغيرات "thread_local" تقلل من مشاكل التزامن، إلا أنه يجب الحذر عند التعامل مع الموارد المشتركة بين الخيوط.

## ملخص بجملة واحدة
تُستخدم "thread_local" في C++ لتعريف متغيرات خاصة بكل خيط، مما يوفر نسخًا مستقلة لكل خيط ويقلل من مشاكل التزامن.