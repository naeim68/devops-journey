# 🧪 Lab 01 — Mount Persistence

## 🎯 هدف
- Mount کردن پارتیشن و پایدارسازی آن پس از ریبوت با `/etc/fstab`

## گام‌ها
1. شناسایی پارتیشن:
```bash
lsblk -f
```
2. گرفتن UUID:
```bash
tune2fs -l /dev/sdb5 | grep UUID
```
3. Mount موقت:
```bash
sudo mkdir -p /mnt/data
sudo mount /dev/sdb5 /mnt/data
```
4. ثبت در `/etc/fstab` (با UUID):
```
UUID=<YOUR-UUID>  /mnt/data  ext4  defaults  0  2
```
5. اعتبارسنجی:
```bash
sudo mount -a
df -h | grep /mnt/data
```

## Cleanup (اختیاری)
- حذف Mount Point یا کامنت‌کردن خط fstab.
