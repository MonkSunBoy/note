# Archlinux Note

## SquashFS
SquashFS 是一个只读文件系统 [SquashFS}(https://zh.wikipedia.org/wiki/SquashFS)

## dd 制作LiveUSB
使用dd命令制作LiveUSB [dd](https://wiki.archlinux.org/index.php/USB_flash_installation_media_%28%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87%29#GNU.2FLinux)

## install VBoxLinuxAddition
[教程](http://www.hiroom2.com/2016/06/06/archlinux-install-virtualbox-guest-additions/)

## config sddm
[xinitrc](https://wiki.archlinux.org/index.php/Xinit#Autostart_X_at_login)

## 字体

安装常用的英文字体和中文字体，个人很喜欢adebe的source系列开源字体，安装:

sudo pacman -S ttf-dejavu wqy-microhei
sudo pacman -S adobe-source-code-pro-fonts \
          adobe-source-sans-pro-fonts \
          adobe-source-serif-pro-fonts \
          adobe-source-han-sans-cn-fonts

yaourt ttf-monaco

## 输入法

个人喜欢使用fcitx框架，在此框架下提供的中文输入法比较好用，这里只选择安装sogou输入法:

sudo pacman -S fcitx fcitx-im fcitx-qt5 fcitx-configtool
