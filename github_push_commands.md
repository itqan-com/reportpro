# أوامر رفع تطبيق reportpro إلى GitHub

**التاريخ:** 2026-04-16  
**المستودع:** https://github.com/itqan-com/reportpro.git  
**الفرع:** `version-16`

---

## الأمر الأول — فحص حالة المشروع

```bash
cd /home/erp16/frappe-bench-16/apps/reportpro && git status && git remote -v
```

**الغرض:** التحقق من حالة الكود وما إذا كان هناك remote مضاف مسبقاً.

**النتيجة:** الكود نظيف ولا يوجد أي remote.

---

## الأمر الثاني — إضافة الـ Remote

```bash
cd /home/erp16/frappe-bench-16/apps/reportpro && git remote add origin https://github.com/itqan-com/reportpro.git && git remote -v
```

**الغرض:** ربط المشروع المحلي بمستودع GitHub.

**النتيجة:** تم إضافة الـ remote بنجاح.

---

## الأمر الثالث — رفع الكود (المحاولة الأولى - فشلت)

```bash
cd /home/erp16/frappe-bench-16/apps/reportpro && git push -u origin version-16
```

**الغرض:** رفع الفرع `version-16` إلى GitHub.

**النتيجة:** ❌ فشل بسبب عدم وجود صلاحية للمستخدم `aliahmedprositeyemen` على مستودع `itqan-com`.

**سبب الفشل:**
```
remote: Permission to itqan-com/reportpro.git denied to aliahmedprositeyemen.
fatal: unable to access 'https://github.com/itqan-com/reportpro.git/': The requested URL returned error: 403
```

**الحل:** تم الدخول إلى إعدادات المستودع على GitHub وإضافة المستخدم كـ Collaborator:  
`https://github.com/itqan-com/reportpro/settings/access`

---

## الأمر الرابع — رفع الكود (المحاولة الثانية - نجحت)

```bash
cd /home/erp16/frappe-bench-16/apps/reportpro && git push -u origin version-16
```

**الغرض:** إعادة الرفع بعد إضافة الصلاحيات.

**النتيجة:** ✅ تم الرفع بنجاح

```
Enumerating objects: 23, done.
Counting objects: 100% (23/23), done.
Compressing objects: 100% (17/17), done.
Writing objects: 100% (23/23), 8.88 KiB | 1.78 MiB/s, done.
Total 23 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/itqan-com/reportpro.git
 * [new branch]      version-16 -> version-16
branch 'version-16' set up to track 'origin/version-16'.
```

---

## ملاحظة

الأمران الثالث والرابع متطابقان، لكن الفرق هو أنه تم إضافة الصلاحية على GitHub بينهما، مما أتاح نجاح العملية في المحاولة الثانية.
