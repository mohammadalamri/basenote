Basenote — Repository package (ملفات جاهزة لرفع Webflow وتشغيل محلي)

محتويات الحزمة
- صفحات ستاتيك: index.html, about.html, services.html, blog.html, contact.html
- ملفات واجهة: styles.css, scripts.js
- backend scaffold: backend/server.js, backend/package.json, backend/.env.example, backend/db/schema.sql
- CSVs للـ Webflow CMS: cms/posts.csv, cms/services.csv, cms/authors.csv, cms/testimonials.csv
- سكربتات لعمل mirror و استبدال الأسماء (إن أردت نقل من موقع قديم): mirror_site.sh, rename_files.sh, replace_content.js, make_zip.sh
- دليل Webflow مختصر: webflow-setup.md

تعليمات سريعة — إنشاء مستودع جديد ورفع الملفات
1) أنشئ مجلد عمل محلي:
   mkdir basenote && cd basenote

2) انسخ الملفات (أو احفظ كل ملف من هذه المحادثة داخل مجلد basenote مع نفس البنية: cms/, backend/, ...)

3) ابدأ مستودع git وادفعه إلى GitHub
   git init
   git add .
   git commit -m "Initial commit — Basenote starter"
   # أنشئ repo جديد على GitHub (اسم: basenote) عبر واجهة github.com أو استخدم gh cli
   # لو أنشأت الريبو على github.com فستحصل على رابط remote مثل:
   git remote add origin https://github.com/YOUR_USERNAME/basenote.git
   git branch -M main
   git push -u origin main

4) تشغيل الواجهة الستاتيك محلياً
   - افتح index.html في المتصفح مباشرة (Static preview) أو استخدم simple http server:
     python3 -m http.server 8000
     ثم افتح http://localhost:8000

5) تشغيل backend محلياً (نموذج contact)
   cd backend
   npm install
   انسخ ملف .env.example إلى .env وعدّل القيم إن أردت
   npm run dev
   سيعمل السيرفر على http://localhost:8080 (endpoint /api/contact و /api/health)

6) ربط Webflow form بالـ backend أثناء الاختبار المحلي
   - شغّل ngrok: ngrok http 8080
   - خذ الرابط العام https://abcd1234.ngrok.io واستخدمه كـ form action: https://abcd1234.ngrok.io/api/contact
   - بدلاً من ngrok يمكنك استخدام Webflow built-in forms أو Zapier لربط الفورم إلى endpoint خارجي.

إذا تريد ZIP جاهز أو أن أجهّز الريبو وأدفعه لك، أحتاج صلاحية لإنشاء المستودع (لا أملكها الآن). بدلاً من ذلك يمكنني توليد ملف ZIP هنا — اطلب "أعطني ZIP".