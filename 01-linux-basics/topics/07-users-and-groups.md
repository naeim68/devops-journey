# 👤 مدیریت کاربران و گروه‌ها

## دستورات پایه
| دستور | توضیح | مثال |
|:--|:--|:--|
| `sudo -i` | ورود به محیط root | — |
| `passwd [username]` | تغییر/تنظیم پسورد | `passwd naeim` |
| `su -` | سوییچ کاربر | `su - root` |
| `whoami` | نمایش کاربر فعلی | `whoami` |

## Authentication
- Password-Based، Certificate-Based، Kerberos، Smart Card-Based

## فایل‌های کلیدی
- `/etc/passwd`, `/etc/shadow`, `/etc/group`, `/etc/gshadow`

نمونه `/etc/passwd`:
```bash
naeim:x:1002:1002::/home/naeim:/bin/bash
```

## انواع حساب و محدوده UID
- System، Application، User Defined  
- UID: 0–999 سیستمی/برنامه‌ای، 1000+ کاربر تعریف‌شده

## گروه‌ها و کاربران
ایجاد گروه:
```bash
groupadd IT
groupadd web
groupadd developer
```
ساخت کاربر:
```bash
useradd -d /home/farhad -m -g IT -G web,developer -c "farhad yousefi" -s /bin/bash farhad
passwd farhad
```
سوییچ‌ها: `-d` home، `-m` ایجاد پوشه، `-g` گروه اصلی، `-G` فرعی‌ها، `-c` توضیح، `-s` شل.

مدیریت:
```bash
usermod -L farhad
usermod -U farhad
userdel -r farhad
```

Shadowing:
```bash
pwunconv   # غیرفعال
pwconv     # فعال
grpunconv  # غیرفعال گروه‌ها
grpconv    # فعال گروه‌ها
```

پسورد گروه:
```bash
gpasswd IT
gpasswd Developer
```

ساخت کاربر با پسورد هش‌شده:
```bash
useradd -d /home/naeim -m -g developer -G IT,web -p $(mkpasswd -m sha-512 "linux") -s /bin/bash naeim
```
