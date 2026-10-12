# المراجع التقنية — مؤذّن

هذه المراجع تسند اختيارات التنفيذ؛ لا تعني أن اختبارًا على جهاز Android قد أُجري.

## حساب مواقيت الصلاة

- [adhan-js — Batoul Apps](https://github.com/batoulapps/adhan-js): مكتبة الحساب المستخدمة في الويب، مثبتة في المشروع بالإصدار `adhan@4.4.6`، وتعمل محليًا مع إحداثيات المدينة وطريقة الحساب.
- [adhan-kotlin — Batoul Apps](https://github.com/batoulapps/adhan-kotlin): مصدر مكتبة Android الأصلية، مع اعتماد Gradle `com.batoulapps.adhan:adhan2:0.0.7`. يستخدم مسار الجدولة هذا الحساب المحلي بعد إقلاع الجهاز أيضًا، بدل الاعتماد على JavaScript.

## Android: المنبهات وخدمة الوسائط

- [Alarms | Android Developers](https://developer.android.com/develop/background-work/services/alarms): مرجع `AlarmManager` والمنبهات الدقيقة والقيود المتعلقة بحالة الطاقة.
- [Schedule exact alarms | Android 14 changes](https://developer.android.com/about/versions/14/changes/schedule-exact-alarms): يوضح تغييرات الإذن الخاص بالتنبيهات الدقيقة في Android 14 وما بعده. يجب أن يمنح المستخدم الإذن المناسب من إعدادات النظام؛ والبناء وحده لا يثبت سلوك التنبيه على كل جهاز.
- [Foreground service types: media playback](https://developer.android.com/develop/background-work/services/fgs/service-types): مرجع متطلبات نوع خدمة `mediaPlayback` عند تشغيل ملف الوسائط مع استمرار العمل خارج الواجهة.

يتضمن المشروع حارس إذن Android، وجدولة محلية، وخدمة تشغيل أصلية، ومستقبلات الإقلاع/التاريخ/الوقت/المنطقة الزمنية. وضع Doze وسياسات البطارية والشركات المصنّعة قد تغيّر السلوك؛ لذلك يلزم اختبار حقيقي مع قفل الشاشة وبعد إعادة التشغيل وتغيير المنطقة الزمنية قبل وصف الخلفية بأنها مؤكدة على جهاز معين.

## الويب وPWA

- [Service workers | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API): شرح عامل الخدمة والتخزين الشبكي/المحلي.
- التسجيلات في هذا المشروع مخزنة محليًا بعد تحميل النسخة عبر HTTPS وزيارة التطبيق مرة على الأقل. يحسب الويب المواقيت في المتصفح، لكن المتصفح **لا يضمن** إطلاق صوت في الوقت المحدد إذا عُلّقت الصفحة أو أُغلقت؛ الأذان الخلفي الحقيقي مطلوب له مسار Android الأصلي.
