# 如何在Linux或者Windows的Vbox里头安装运行Mac OS X

## 准备
安装之前需要先安装这些东西

安装VirtualBox，我用的 5.0.14
安装VirtualBox extension
在Vbox里头新建一个虚机，选64位mac os x，选el capitan 64位，假设你把虚机命名为 "el capitan"
生成磁盘文件，建议至少给10G
生成一个 El Capitan 的iso
把iso设置到上面虚机的光驱上
在 Vbox 的系统（system）设置界面，把软驱启动去掉
还是在系统设置里头，把主板芯片组设置成　PIIX3，不要用 ICH9
内存给 2G
显存给32M或者64M
上面的都做完了，就执行下面的配置

## 配置
打开一个终端，运行下面命令，注意把下面的“el captian”改成你在前头第一步给虚机命名的名字：

VBoxManage modifyvm "el capitan" --cpuidset 00000001 000106e5 00100800 0098e3fd bfebfbff
VBoxManage setextradata "el capitan" "VBoxInternal/Devices/efi/0/Config/DmiSystemProduct" "iMac11,3"
VBoxManage setextradata "el capitan" "VBoxInternal/Devices/efi/0/Config/DmiSystemVersion" "1.0"
VBoxManage setextradata "el capitan" "VBoxInternal/Devices/efi/0/Config/DmiBoardProduct" "Mac-F2238BAE"
VBoxManage setextradata "el capitan" "VBoxInternal/Devices/smc/0/Config/DeviceKey" "ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc"
VBoxManage setextradata "el capitan" "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC" 1

## 安装
上面的做完之后就可以点击启动安装啦，基本就是mac的安装过程， mac 启动之后，进去要先去磁盘工具选择前面初始化的磁盘设备初始化一下（抹掉，弄成osx 日志文件系统，给卷标），然后各种同意、下一步、安装即可。
