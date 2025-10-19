# 💽 پارتیشن‌بندی و فایل‌سیستم‌ها

## Partition Tables
| نوع | ویژگی | محدودیت |
|:--|:--|:--|
| MBR | مناسب < 2TB | حداکثر 4 Primary |
| GPT | مناسب ≥ 2TB | تا 128 پارتیشن |

## انواع پارتیشن در MBR
- Primary، Extended (حاوی Logical)، Logical (از `/dev/sdb5` به بعد)

## شناسایی دیسک/پارتیشن
```bash
fdisk -l /dev/sda
ls /dev
ls /dev/sd*
lsblk
```

## فایل‌سیستم‌ها
| نوع | ویژگی |
|:--|:--|
| ext2/3/4 | ext4 سریع و پایدار |
| btrfs | مدرن، نیازمند Kernel ≥ 3.10 |
| reiserfs | inode زیاد |
| vfat | سازگار با Windows |
| iso9660 | CD/DVD |
| nfs | شبکه‌ای |
| swap | فضای مبادله |
| proc | مجازی |

## فرمت کردن
```bash
mkfs -t ext4 /dev/sdb1
mkfs.ext4 /dev/sdb6
```

## نمایش فایل‌سیستم‌ها
```bash
lsblk -f
```

## UUID و Label
نمایش UUID:
```bash
tune2fs -l /dev/sdb5 | grep UUID
```
ست‌کردن Label:
```bash
tune2fs -L music /dev/sdb1
```
