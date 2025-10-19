# 📂 مدیریت پوشه‌ها و فایل‌ها

| دستور | عملکرد | مثال |
|:--|:--|:--|
| `mkdir [name]` | ساخت دایرکتوری | `mkdir test` |
| `rmdir [name]` | حذف دایرکتوری خالی | `rmdir emptydir` |
| `rm -r [path]` | حذف بازگشتی | `rm -r oldproject` |
| `mkdir -p a/b/c` | ساخت تو در تو | `mkdir -p projects/devops/day1` |
| `touch [file]` | ایجاد/به‌روزرسانی زمان | `touch notes.txt` |
| `cat [file]` | نمایش محتوا | `cat notes.txt` |
| `echo "text"` | چاپ متن | `echo "Hello Linux"` |
| `echo "t" > f` | بازنویسی در فایل | `echo "new" > file.txt` |
| `echo "t" >> f` | افزودن به انتها | `echo "append" >> file.txt` |
| `ls` / `-a` / `-lh` / `-R` | لیست و جزئیات | `ls -lha` |

## 📂 دستور ls و ساختار خروجی
نمونه:
```bash
drwxr-xr-x 2 naeim staff 4096 Oct 6 09:42 projects
```
- کاراکتر اول نوع فایل: `-` معمولی، `d` دایرکتوری، `l` لینک نمادین، `b` بلاک، `c` کاراکتری، `s` سوکت.

## 🔗 لینک‌ها
| نوع | توضیح | ساخت |
|:--|:--|:--|
| Hard Link | اشاره به inode اصلی | `ln file1.txt link1.txt` |
| Soft Link | اشاره به مسیر | `ln -s file1.txt symlink1.txt` |

## ستون‌های دیگر در `ls -l`
3) Owner، 4) Group Owner، 5) Size، 6) Date&Time، 7) Name  
جزئیات بیشتر:
```bash
stat file2.txt
```

## سه نوع زمان فایل
- atime (دسترسی) — mtime (تغییر محتوا) — ctime (تغییر متادیتا)
