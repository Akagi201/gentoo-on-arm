# gentoo-on-arm

ARM and ARM64 are supported by the Gentoo project but do not yet have a full handbook at their disposal. Please refer to the [ARM project](https://wiki.gentoo.org/wiki/Project:ARM) for more information.

Notes: MIPS has good documents, may be used for references.

## China official Gentoo mirrors

Name              | Protocol | IPv4/v6 | URL
------------------|----------|---------|------
Xiamen University | ftp      | IPv4 + IPv6 | <ftp://mirrors.xmu.edu.cn/gentoo>
Xiamen University | http     | IPv4 + IPv6 | <http://mirrors.xmu.edu.cn/gentoo>
Xiamen University | rsync    | IPv4 + IPv6 | <rsync://mirrors.xmu.edu.cn/gentoo/>

* livecd: <http://mirrors.xmu.edu.cn/gentoo/releases/amd64/autobuilds/current-install-amd64-minimal/>
* stage3: <http://mirrors.xmu.edu.cn/gentoo/releases/amd64/autobuilds/current-install-amd64-minimal/>
* for distfile: `make.conf` -> `GENTOO_MIRRORS`
* for portage: `repos.conf` -> `SYNC`

## USE
* The default USE settings are placed in the make.defaults files of the Gentoo profile used by the system.
* Check the currently active USE settings: `emerge --info | grep ^USE`
* USE flags full description: `/usr/portage/profiles/use.desc`
* Users who want to ignore any default USE settings and manage it completely themselves should start the USE definition in make.conf with -*: `USE="-* X acl alsa ..."`

## useful apps
* dracut

## systemd

* REQUIREMENTS: <http://cgit.freedesktop.org/systemd/systemd/tree/README>
* <https://wiki.gentoo.org/wiki/Systemd>

### packages
* systemd-sysv-utils

## kernel
### packages
* MCE: app-admin/mcelog

### configs
* Support docker, FUSE, mac, 32bit, ext2, systemd

* File systems ---> 

```
Second extended fs support
  Ext2 extended attributes
    Ext2 POSIX Access Control Lists
    Ext2 Security Labels
  Ext2 execute in place support
....
FUSE (Filesystem in Userspace) support
  Character device in Userspace support
```

* Device Drivers --->

```
Thunderbolt support for Apple devices
```

* Executable file formats / Emulations --->

```
IA32 Emulation
  IA32 a.out support
  x32 ABI for 64-bit mode
```

* Processor type and features --->

```
EFI runtime service support
  EFI stub support
    EFI mixed-mode support
```

* docker related config

```
CONFIG_AUTOFS4_FS
CONFIG_CGROUP_FREEZER
CONFIG_CGROUP_DEVICE (needed)
CONFIG_RESOURCE_COUNTERS (needed)
CONFIG_CGROUP_SCHED (needed)
CONFIG_CGROUP_PERF (needed)
CONFIG_FANOTIFY (needed)
CONFIG_GENTOO_LINUX_INIT_SYSTEMD (needed)
CONFIG_IPV6
CONFIG_CMDLINE_BOOL
```

* systemd related config

```
General setup  --->
  Configure standard kernel features (expert users)  --->
```

### kernel modules
* List the modules that need to be loaded automatically in `/etc/conf.d/modules`.
* Add modules to auto loads. `nano -w /etc/conf.d/modules`, `modules="3c59x"`



























