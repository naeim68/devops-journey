# 🧪 Lab 02 — Permissions Practical

## 🎯 هدف
- تمرین مالکیت، مجوزها و بیت‌های خاص

## سناریو
1. ساخت ساختار آزمایش:
```bash
mkdir -p /tmp/perm-lab && cd /tmp/perm-lab
touch a.sh b.txt
groupadd -f devs
useradd -M -N -s /usr/sbin/nologin tempuser || true
```
2. مالکیت و مجوزها:
```bash
chown tempuser:devs a.sh
chmod 640 b.txt
chmod 755 a.sh
```
3. بیت‌های خاص:
```bash
chmod u+s a.sh   # SUID
mkdir shared && chmod 1777 shared  # Sticky
```
4. انتقال مجوز از الگو:
```bash
chmod --reference=a.sh b.txt
```
5. بررسی:
```bash
ls -l
namei -om a.sh || true
```

## پاکسازی
```bash
userdel -r tempuser 2>/dev/null || true
rm -rf /tmp/perm-lab
```
