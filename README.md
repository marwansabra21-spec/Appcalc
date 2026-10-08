# Plan Calc – APK

## بناء الـ APK على GitHub (من غير Android Studio)
1. اعمل repository جديد على GitHub وارفع كل محتويات الفولدر ده (بما فيها `.github`).
2. افتح تاب **Actions** > **Build APK** > **Run workflow** (أو أي push على main بيشغّله).
3. بعد ما يخلص (حوالي 5-8 دقايق) افتح الـ run ونزّل **plancalc-apk** من Artifacts. جواه `app-debug.apk`.
4. انقله للموبايل وسطّبه (لازم تفعّل "تثبيت من مصادر غير معروفة").

## البناء على جهازك
```
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
```
الناتج: `android/app/build/outputs/apk/debug/app-debug.apk`

## ملاحظات
- التطبيق شغال بدون إنترنت: three.js متضمّن، والحساب بنفس المعادلة `(plan × 100) ÷ 70 + 5` على الجهاز.
- سيرفر C++ (`server.cpp`) مش داخل الـ APK. هو للتشغيل على الكمبيوتر فقط.
- ده debug APK للتجربة. للنشر على Google Play محتاج release موقّع.
