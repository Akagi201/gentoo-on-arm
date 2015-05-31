1. Download livecd: <http://mirrors.xmu.edu.cn/gentoo/releases/amd64/autobuilds/current-install-amd64-minimal/install-amd64-minimal-20150528.iso>
2. Create virtualbox virtual machine. 2g ram, 50g disk.
3. Config virtualbox settings, network: bridge, cpu, display, boot sequence, usb.
4. Attach iso file, check livecd.
5. Power on -> gentoo(twice enter)
6. ifconfig -> enp0s3
7. parted -a optimal /dev/sda
8. mklabel gpt
9. unit mib
10. mkpart primary 1 3
11. name 1 akgrub
12. set 1 bios_grub on
13. mkpart primary 3 1027
14. name 2 akboot
15. mkpart primary 1027 3075
16. name 3 akswap
17. mkpart primary 3075 -1
18. name 4 akrootfs
19. set 2 boot on
20. print
21. quit
22. mkfs.vfat /dev/sda2
23. mkfs.ext4 /dev/sda4
24. mkswap /dev/sda3
25. swapon /dev/sda3
26. mount /dev/sda4 /mnt/gentoo
27. mkdir /mnt/gentoo/boot
28. mount /dev/sda2 /mnt/gentoo/boot
29. date MMDDhhmmYYYY, use UTC timezone
30. cd /mnt/gentoo
31. wget http://mirrors.xmu.edu.cn/gentoo/releases/amd64/autobuilds/current-install-amd64-minimal/stage3-amd64-20150528.tar.bz2
32. tar xvjpf stage3-*.tar.bz2 --xattrs
33. nano -w ./etc/portage/make.conf
```
CFLAGS="-march=native -O2 -pipe"
MAKEOPTS="-j5"
ACCEPT_LICENSE="*"
ACCEPT_KEYWORDS="~amd64"
USE="-consolekit systemd"
```
34. set mirrors
35. cp -L /etc/resolv.conf /mnt/gentoo/etc/
36. mount -t proc proc /mnt/gentoo/proc
37. mount --rbind /sys /mnt/gentoo/sys
38. mount --make-rslave /mnt/gentoo/sys
39. mount --rbind /dev /mnt/gentoo/dev
40. mount --make-rslave /mnt/gentoo/dev
41. chroot /mnt/gentoo /bin/bash
42. source /etc/profile
43. export PS1="(chroot) $PS1"
44. emerge-webrsync
45. eselect news read
46. emerge --sync
47. eselect profile set 3 (desktop, install awesome later)
48. echo "Asia/Shanghai" > /etc/timezone
49. emerge --config sys-libs/timezone-data
50. nano -w /etc/locale.gen

```
en_US.UTF-8 UTF-8
zh_CN.UTF-8 UTF-8
zh_CN.GBK GBK
```

51. locale-gen
52. locale -a
53. eselect locale list
54. eselect locale set 3 -> en_US.UTF-8 UTF-8
55. env-update && source /etc/profile
56. export PS1="(chroot) $PS1"
57. emerge --ask sys-kernel/gentoo-sources
58. ls -l /usr/src/linux
59. emerge --ask sys-apps/pciutils
60. cd /usr/src/linux
61. make menuconfig
62. <https://wiki.gentoo.org/wiki/Kernel/Gentoo_Kernel_Configuration_Guide>
63. 