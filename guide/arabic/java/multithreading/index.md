---
title: Multithreading
localeTitle: خاصية تعدد
---## خاصية تعدد

يعد تعدد العمليات عملية تنفيذ عمليات متعددة في نفس الوقت. تقوم Java بتشغيل البرنامج باستخدام مؤشر ترابط رئيسي وإضافة المزيد من مؤشرات الترابط إلى مؤشر ترابط رئيسي عند إنشاء أي مستخدم له. الموضوع الرئيسي هو أول موضوع المستخدم في أي برنامج جافا. أيضا ، JVM يتأكد من أن جميع المواضيع المستخدم مغلقة قبل انتهاء البرنامج.

الخيط له مزايا وعيوب.

## مزايا:

*   تشغيل التعليمات البرمجية بشكل مستقل عن مؤشرات الترابط الأخرى.
*   خلق تصميم وحدات.

## سلبيات:

حالات السباق و Deadlocks إذا لم يتم syncrhronized مؤشرات الترابط بشكل صحيح.

يمكن تقسيم الخيوط إلى فئتين:

*   المواضيع العضو
*   خيوط الشيطان

يمكن إنشاء مؤشر ترابط بطريقتين:

1.  تنفيذ واجهة Runnable: هناك طريقة واحدة فقط في واجهة Runnable أي تشغيل void العام (). سيضمن تنفيذ هذا الأسلوب أنه عند بدء تشغيل مؤشر الترابط ، يتم تنفيذ التعليمة البرمجية داخل run ().
    
2.  تمديد فئة الموضوع. يحتوي هذا الفصل أيضًا على تشغيل void عام () والذي نحتاج إلى تجاوزه لتشغيل الكود الخاص بنا. تتمثل عيوب استخدام هذه الطريقة في أن لدينا فئة مميزة في سلسلة الرسائل ولا يمكننا توسيع أي فئة أخرى قد نريدها.
    

يمكن العثور على الكود لكليهما: http://ide.geeksforgeeks.org/k7GjcA.

ستلاحظ أنه إذا تم تشغيل هذا الرمز عدة مرات ، فقد تختلف النتائج. ويتم تحديد ذلك من قبل نظام التشغيل الذي يتم تشغيله. يمكن لنظام التشغيل اختيار أي مؤشر ترابط من حالة runnable ويمكن تشغيله. نحن hsve أي السيطرة على ذلك. إذا كان هناك العديد من مؤشرات الترابط في حالة runnable (جاهز للتشغيل) ، يمكن اختيار أي شخص. حتى لا تعتمد على الأولوية.

مزيد من التفاصيل: https://www.ntu.edu.sg/home/ehchua/programming/java/J5e\_multithreading.html