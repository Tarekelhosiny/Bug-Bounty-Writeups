# 🛡️ Web Vulnerability Report

## 📌 اسم الثغرة:
SQL Injection – استرجاع بيانات مخفية  
(SQL Injection – Retrieve Hidden Data)

## 🌍 اسم المختبر:
PortSwigger Lab – SQL Injection في جملة WHERE لاسترجاع بيانات مخفية

## 🧠 وصف الثغرة:
الثغرة موجودة في استعلام SQL داخل جملة WHERE للفلترة حسب category. من خلال إدخال كود خبيث في باراميتر category، يمكن تجاوز شرط الفلترة واسترجاع جميع البيانات بما فيها المخفية.

## 🛠️ خطوات استغلال الثغرة:
1. فتح صفحة المنتجات في الكاتيجوري "Accessories".
2. تعديل قيمة الباراميتر category في الرابط إلى:  
Accessories' OR 1=1--

3. تحديث الصفحة، مما أدى إلى عرض كل المنتجات بغض النظر عن الكاتيجوري.

## 📸 صورة من العملية:
![SQL Injection screenshot](screenshot.png)

## 💣 التأثير (Impact):
- عرض بيانات غير مصرح بها للمستخدم.
- تهديد لسرية وأمان قاعدة البيانات.

## 🔧 الحل المقترح (Fix):
- استخدام Prepared Statements أو Parameterized Queries.
- فلترة وفحص الإدخالات بشكل صارم.
- تركيب جدار حماية للتطبيقات (WAF).

## 👨‍💻 كاتب التقرير:
طارق – Web Pentester in Training
