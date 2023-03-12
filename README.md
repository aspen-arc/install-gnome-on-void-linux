# install-gnome-on-void-linux
How to install Gnome and GDM in void linux.<br>

# First
Update:
```
$ sudo xbps-install -Suv
```
Then add non-free repo:
```
$ sudo xbps-install -Rs void-repo-nonfree 
```
# Install

Recomended packages:
```
$ sudo xbps-install curl wget git xz unzip zip nano vim gptfdisk xtools mtools mlocate ntfs-3g fuse-exfat bash-completion linux-headers gtksourceview4 ffmpeg mesa-vdpau mesa-vaapi htop
```
Development:
```
$ sudo xbps-install autoconf automake bison m4 make libtool flex meson ninja optipng sassc
```
# Desktop Enviorment
Install:
```
$ sudo xbps-install xorg gnome gdm
```
Enable GDM:
```
$ sudo ln -s /etc/sv/gdm /var/service
```
Install XDG:
```
$ sudo xbps-install -Rs xdg-desktop-portal xdg-desktop-portal-gtk xdg-user-dirs xdg-user-dirs-gtk xdg-utils
```
# Insall required services
```
$ sudo xbps-install -y dbus elogind
```
Enable dbus and elogind
```
$ sudo ln -s /etc/sv/dbus /var/service
$ sudo ln -s /etc/sv/elogind /var/service
```
# NetworkManager
```
$ sudo xbps-install NetworkManager NetworkManager-openvpn NetworkManager-openconnect NetworkManager-vpnc NetworkManager-l2tp
```
Enable NetworkManager:
```
$ sudo ln -sv /etc/sv/NetworkManager /var/service
```
# Audio
```
sudo xbps-install pulseaudio pulseaudio-utils pulsemixer alsa-plugins-pulseaudio
```
# Bluetooth
```
$ sudo xbps-install bluez
```
Enable:
```
$ sudo ln -sv /etc/sv/bluetoothd /var/service
```
Add user to group
```
$ sudo useradd -G bluetooth ${USER}
```
# Printer
```
$ sudo xbps-install cups cups-pk-helper cups-filters foomatic-db foomatic-db-engine
```
Enable:
```
$ sudo ln -sv /etc/sv/cupsd /var/service
```
# Cronie
```
$ sudo xbps-install -y cronie
```
Enable:
```
$ sudo ln -sv /etc/sv/cronie /var/service
```
# Terminal and Web Browser
```
$ sudo xbps-install tilix firefox firefox-i18n-en-US
```
