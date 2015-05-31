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