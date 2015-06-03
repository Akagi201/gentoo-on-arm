109. login with mm
110. sudo emerge wget
111. sudo emerge net-misc/curl
112. /etc/portage/package.use/package.use

```
dev-libs/boost static-libs
dev-vcs/git subversion perl
dev-vcs/subversion perl -dso
```

113. sudo emerge dev-vcs/git
114. sudo emerge subversion
115. sudo emerge dosfstools
116. sudo emerge gentoolkit
117. sudo emerge eix
118. sudo emerge uuid
119. sudo emerge go
120. sudo emerge texinfo
121. sudo emerge bzr
122. sudo emerge ccache
123. sudo emerge samba
124. sudo emerge u-boot-tools
125. sudo emerge colordiff
126. sudo emerge rcs
127. sudo emerge sqlite

```
/etc/dispatch-conf.conf
use-rcs=yes
```

127. sudo emerge colordiff

```
/etc/dispatch-conf.conf
diff="colordiff -Nu '%s' '%s'"
merge="vimdiff -c'saveas %s' -c next -c'setlocal noma readonly' -c prev %s %s"
```

128. sudo emerge samba
129. sudo emerge asciidoc
130. sudo emerge bc
131. sudo emerge binutils
132. sudo emerge bzip2
133. sudo emerge fastjar
134. sudo emerge flex
135. sudo emerge util-linux
136. sudo emerge gawk
137. sudo emerge intltool
138. sudo emerge jikes
139. sudo emerge zlib
140. sudo emerge make
141. sudo emerge cdrtools
142. sudo emerge ncurses
143. sudo emerge openssl
144. sudo emerge patch
145. sudo emerge perl-ExtUtils-MakeMaker
146. sudo emerge rsync
147. sudo emerge ruby
148. sudo emerge sdcc
149. sudo emerge unzip
150. sudo emerge gettext
151. sudo emerge libxslt
152. sudo emerge boost-build
153. sudo emerge XML-Parser
154. sudo emerge libusb-compat
155. sudo emerge bin86
156. sudo emerge dev86
157. sudo emerge sharutils
158. sudo emerge oracle-jdk-bin
159. sudo emerge b43-fwcutter
160. sudo emerge lua
161. sudo emerge libuv
162. sudo emerge libpcap
163. sudo emerge doxygen
164. sudo emerge m4
165. sudo emerge boost
166. sudo emerge gengetopt
167. sudo emerge tcpdump
168. sudo emerge colorsvn

## samba
* cd /etc/samba
* sudo systemctl enable smbd.service
* /etc/samba/smb.conf

```
security = user
[home]
browseable = yes
read only = no
create mask = 0644
directory mask = 0755
```

* sudo pdbedit -a -u mm
* spf13

## ssh
* `ssh-keygen -t rsa -b 4096 -C "akagi201@gmail.com"`
* 

## python pip
* pip: `sudo emerge -a dev-python/pip`
* virtualenv: `sudo emerge -a virtualenv`
* virtualenvwrapper: `sudo emerge -a virtualenvwrapper`

## awesome
* sudo emerge -a awesome
* mkdir -p ~/.config/awesome/
* cp /etc/xdg/awesome/rc.lua ~/.config/awesome/rc.lua
* sudo emerge xterm
* awesome -k
* sudo emerge -a feh
* kernel config

```
nVidia settings
Device Drivers --->
  Graphics support --->
    Direct Rendering Manager (XFree86 4.1.0 and higher DRI support) --->
    <*>    Nouveau (nVidia) cards
```

* /etc/portage/make.conf

```
INPUT_DEVICES="evdev"
VIDEO_CARDS="virtualbox"
```

* sudo emerge --ask x11-base/xorg-server
* echo XSESSION="awesome" > /etc/env.d/90xsession
* env-update && source /etc/profile
* //emerge x11-drivers/nvidia-drivers
* //nvidia-xconfig
* //eselect opengl set nvidia
* sudo emerge 
* sudo emerge --update --deep --newuse world
* sudo emerge =virtualbox-guest-additions-4.3.28
* sudo gpasswd -a mm vboxguest
