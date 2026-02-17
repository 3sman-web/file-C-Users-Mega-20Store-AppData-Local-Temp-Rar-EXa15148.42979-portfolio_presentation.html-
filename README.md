README — .htaccess Configuration (Summary)

Purpose: Redirect www → non‑www, force HTTPS, hide .php/.html extensions, preserve SEO.

Files changed: .htaccess in site root (public_html).

What I implemented:
- موحّد التحويل: كل الطلبات تتحول إلى https://example.com/... بدون www.
- عرض صفحات بدون امتدادات: المستخدم يرى /page بينما السيرفر يخدم page.php أو page.html.
- تحويل 301 للروابط القديمة التي تحتوي امتدادات إلى النسخة الجديدة بدون امتداد.
- إزالة trailing slash للملفات غير الدليلية.
- تعطيل عرض محتويات المجلدات.

Testing steps:
1. افتح: http://www.example.com/abc.php  -> يجب أن يتحول إلى https://example.com/abc
2. افتح: http://example.com/xyz.html  -> يجب أن يتحول إلى https://example.com/xyz
3. افتح: https://www.example.com/  -> يجب أن يتحول إلى https://example.com/

Rollback:
- احتفظ بنسخة احتياطية من .htaccess السابقة باسم htaccess_backup_v0.txt
- لاسترجاع الحالة السابقة استبدل الملف الحالي بالنسخة الاحتياطية.

Notes:
- تأكد من تفعيل mod_rewrite على الاستضافة.
- تأكد من وجود الملفات page.php أو page.html فعليًا.
