# 💾 RAM و Swap

RAM برای پردازش‌های فعال است؛ با کمبود RAM از **Swap** روی دیسک کمک می‌گیریم.

## روش‌های ساخت Swap
- کاهش Volume و اختصاص به Swap (LVM)
- دیسک/پارتیشن مجزا
- فایل Swap

### ساخت فایل Swap
```bash
dd if=/dev/zero of=./myswap bs=2G count=1
mkswap ./myswap
swapon ./myswap
swapoff ./myswap
```
افزودن به `/etc/fstab`:
```
/swapfile   none   swap   sw   0   0
```

### پارتیشن Swap
```bash
mkswap /dev/sdb2
swapon /dev/sdb2
swapoff /dev/sdb2
```

وضعیت حافظه/Swap:
```bash
free -h
```
