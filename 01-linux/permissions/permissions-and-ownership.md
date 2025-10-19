# 🔐 مجوزها (Permissions) و مالکیت

نمونهٔ پرمیژن:
```
-rw-r--r--+
```
دو نوع permission: **سنتی** و **خاص (+)**

## ساختار کلی
- `owner`، `group owner`، `other`
- دسترسی‌ها: `r` خواندن، `w` نوشتن، `x` اجرا
  - در پوشه: `x` یعنی اجازهٔ ورود (`cd`)

## مالکیت
```bash
chown user:group file.txt
chown :developer f1.txt
```

## تغییر مجوزها با `chmod`
### Symbolic
```bash
chmod o+r file1
chmod g+w file1
chmod a+x file1
chmod o-x file1
chmod g=r file1
chmod u-x,g-w,o+r file1
```
### Numeric
- 4: r، 2: w، 1: x  
مثال: `chmod 755 file1` ⇒ `rwxr-xr-x`

## مجوزهای خاص (SUID/SGID/Sticky)
| نوع | نماد | ستون | توضیح |
|:--|:--|:--|:--|
| SUID | s/S | owner | اجرا با مجوز مالک |
| SGID | s/S | group | اجرا با مجوز گروه |
| Sticky | t/T | other | محدودیت حذف در پوشه‌های عمومی |

مثال‌ها:
```bash
chmod u+s file1.txt
chmod g+s file1.txt
chmod o+t dir1
chmod 4755 script.sh
```

## umask (مجوز پیش‌فرض)
- فایل: 0666، پوشه: 0777  
مثال: `umask 0022` ⇒ فایل جدید 0644  
تغییر: `umask 0002`

## انتقال پرمیژن
```bash
chmod --reference=./d1 f*
```

## Sticky Bit رایج
پوشهٔ `/tmp` معمولاً Sticky دارد.
