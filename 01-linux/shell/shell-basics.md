# 💻 ساختار خط فرمان (Command Prompt Structure)

```bash
root@ubuntuDesktop:~#
```
- `root`: نام کاربر فعلی
- `ubuntuDesktop`: نام میزبان (hostname)
- `~`: دایرکتوری فعلی (Home)
- `#`: کاربر ریشه (root) — پایان پرامپت
- `$`: کاربر معمولی — پایان پرامپت

## 🧭 دستورهای مرتبط با سیستم و مسیرها
| دستور | توضیح | مثال |
|:--|:--|:--|
| `hostname` | نمایش نام سیستم | `hostname` |
| `hostnamectl set-hostname [newname]` | تغییر نام سیستم | `sudo hostnamectl set-hostname devops-lab` |
| `file [path]` | تشخیص نوع فایل | `file /etc/passwd` |
| `pwd` | مسیر فعلی | `pwd` |

## 📘 کمک و مستندات
| دستور | توضیح | مثال |
|:--|:--|:--|
| `man [command]` | راهنمای کامل | `man ls` |
| `[command] --help` | راهنمای خلاصه | `ls --help` |

## ⚙️ نکات تکمیلی و ریدایرکت‌ها
- `sudo` برای دستورات مدیریتی.
- هر دستور دو خروجی دارد: **stdout** و **stderr**.
- نمونهٔ ریدایرکت:
```bash
ls /root >output.txt 2>error.txt
```
