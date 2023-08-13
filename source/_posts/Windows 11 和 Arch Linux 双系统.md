---
title: Windows 11 和 Arch Linux 双系统
urlname: uz6vp5
date: "2022-04-30 21:51:00"
updated: "2022-04-30 21:51:00"
trans: Dual_Booting_Windows_11_and_Arch_Linux
cover: "https://img.imql.life/Dual_Booting_Windows_11_and_Arch_Linux.png"
tags:
  - Arch Linux
  - Windows
categories:
  - PC
---

还不会安装 Linux？快点进来！

<!-- more -->

## 下载系统镜像

[前往官方下载地址](https://archlinux.org/download/)，我使用的 HTTP 下载：
![HTTP下载.png](https://img.imql.life/illustrations/5f9604e4d1e2035a5ff78a3b85b87788.png)

## 磁盘管理

使用 Windows 的磁盘管理从 D 盘分 170GB 空闲空间出来，如下图。
![170GB.png](https://img.imql.life/illustrations/2fd0e04e9af29291bffdcec0dbbbf57b.png)

## 制作启动盘

空 U 盘插入电脑，如下图，使用 [Rufus](https://rufus.ie/) 制作，注意分区类型为 GPT 而非默认的 MBR，写入方式为推荐的 ISO。
![制作.png](https://img.imql.life/illustrations/2412b18d9fa8a94c497d32e2d2a0b562.png)
![以ISO镜像模式写入.png](https://img.imql.life/illustrations/93b5e0f1e7a6bfb5b9c7a80b05843346.png)

## 禁用快速启动和休眠[^1]

![禁用快速启动和休眠.png](https://img.imql.life/illustrations/150747027b71d50cdd6271273704fc96.png)

## 时间表示标准统一[^2]

Windows 默认使用的时间表示标准为 localtime，Arch Linux 默认为 UTC。在此修改 Windows 的为 UTC 以保持统一，Windows 11 中执行如下命令。

```powershell
reg add "HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TimeZoneInformation" /v RealTimeIsUniversal /d 1 /t REG_DWORD /f
```

重新启动 Windows 11 生效。

## BIOS 设置确认

启动盘插入电脑，重启电脑，同时不停按 F2 进入 BIOS，确认以下几点：

- 引导模式为 UEFI；
- 禁用 Secure Boot；
- 如果硬盘是 NVMe 的，硬盘的启动方式需为 AHCI。

## 从 U 盘启动

F10 保存退出 BIOS 后不停按 F12 进入启动项选择界面，键盘上下键选择带“EFI”“USB”字样的，一般是第二个，等待。
下面就可以正式开始安装 Arch Linux：
![正式开始安装.png](https://img.imql.life/illustrations/3bfe20f3ff7d2cf9156a866c1d59c458.png)

## 验证引导模式

要验证引导模式，执行下列命令列出 efivars 目录。

```bash
ls /sys/firmware/efi/efivars
```

如果命令结果显示了目录且没有报告错误，则系统以 UEFI 模式引导。

## 连接无线网

进入交互式提示符（interactive prompt）：

```bash
iwctl
```

列出所有 WiFi 设备：

```bash
device list
```

我的网卡名字为 wlan0，扫描：

```bash
station wlan0 scan
```

列出所有可用的网络：

```bash
station wlan0 get-networks
```

连接到一个网络：

```bash
station wlan0 connect <Network name>
```

输入密码后回车，没有提示的话就是连接成功了，可执行下列命令查看连接状态。

```bash
station wlan0 show
```

退出交互式提示符：

```bash
exit
```

## 更新系统时间

使用 timedatectl 确保系统时间是准确的：

```bash
timedatectl set-ntp true
```

## 建立硬盘分区

查看分区情况：

```bash
lsblk
```

我的硬盘名字为 nvme0n1，使用 cfdisk 进行管理：

```bash
cfdisk /dev/nvme0n1
```

找到以上分出来的 170GB 的空闲空间，选择 New，首先是给根分区分配 32GB，再选择剩下的 138GB，如下图。
![剩下的138GB.png](https://img.imql.life/illustrations/384e65272ef67709711fbee3f123d5a4.png)
选择 New，给交换分区分配 3GB，选择 Type，设定分区类型为 Linux swap，如下图。
![Linux_swap.png](https://img.imql.life/illustrations/2d008cc243095a670e9c25fc1852ba9c.png)
选择剩下的 135GB，选择 New，给家分区分配剩下的空间，选择 Type，设定分区类型为 Linux home，如下图。
![Linux_home.png](https://img.imql.life/illustrations/119c382b48d2688c2e433a78f738544b.png)
选择 Write，输入 yes 回车：
![Write.png](https://img.imql.life/illustrations/cf5f129c57f279989af4cdcf2493bae9.png)
选择 Quit 退出。

## 格式化分区

再次查看分区情况，发现多了三个分区：

```bash
lsblk
```

将根分区格式化为 ext4 格式：

```bash
mkfs.ext4 /dev/nvme0n1p5
```

将交换分区格式化：

```bash
mkswap /dev/nvme0n1p6
```

将家分区格式化为 ext4 格式：

```bash
mkfs.ext4 /dev/nvme0n1p7
```

## 挂载分区

将根分区所对应硬盘卷挂载到`/mnt`:

```bash
mount /dev/nvme0n1p5 /mnt
```

激活交换分区：

```bash
swapon /dev/nvme0n1p6
```

建立目录 home：

```bash
mkdir /mnt/home
```

将家分区所对应硬盘卷挂载到目录 home：

```bash
mount /dev/nvme0n1p7 /mnt/home
```

查看硬盘，找到 EFI System 分区所对应硬盘卷为 nvme0n1p1。：

```bash
fdisk -l
```

建立目录 boot：

```bash
mkdir /mnt/boot
```

将 EFI System 分区所对应硬盘卷挂载目录 boot：

```bash
mount /dev/nvme0n1p1 /mnt/boot
```

## 配置镜像

使用 reflector 来获取速度最快的 6 个镜像，并将地址保存至目录 mirrorlist：

```bash
reflector -c China -a 6 --sort rate --save /etc/pacman.d/mirrorlist
```

更新应用软件库（源），检查下载速度：

```bash
pacman -Syy
```

## 安装必需软件包

使用 pacstrap 脚本，安装 base/base-devel 软件包、 Linux 内核、常规硬件的固件、Vim 和 AMD CPU 驱动：

```bash
pacstrap /mnt base base-devel linux linux-firmware vim amd-ucode
```

## 配置系统

### fstab

用以下命令生成文件 fstab（用`-U`设置 UUID）：

```bash
genfstab -U /mnt >> /mnt/etc/fstab
```

检查生成的文件 fstab：

```bash
cat /mnt/etc/fstab
```

切换到装好的系统：

```bash
arch-chroot /mnt
```

### 时区

设置[时区](https://wiki.archlinux.org/title/Time_zone)：

```bash
ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
```

同步硬件时钟：

```bash
hwclock --systohc
```

### 本地化

编辑文件 locale.gen：

```bash
vim /etc/locale.gen
```

取消掉 en_US.UTF-8 UTF-8 和 zh_CN.UTF-8 UTF-8 前的注释（#）。
生成 locale 信息：

```bash
locale-gen
```

创建 [locale.conf(5)](https://man.archlinux.org/man/locale.conf.5) 文件，[设定 LANG 变量](<https://wiki.archlinux.org/title/Locale_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)#%E7%B3%BB%E7%BB%9F%E5%8C%BA%E5%9F%9F%E8%AE%BE%E7%BD%AE>)：

```bash
vim /etc/locale.conf
```

```
LANG=en_US.UTF-8
```

### 网络

创建文件 hostname，自定义设定主机名：

```bash
vim /etc/hostname
```

```
PC-LAPTOP
```

修改文件 hosts：

```bash
vim /etc/hosts
```

增加行如下（中间的空白用 tab 而非空格，PC-LAPTOP 替换为你自己的主机名）。

```diff
# Static table lookup for hostnames.
# See hosts(5) for details.
+
+127.0.0.1       localhost
+::1             localhost
+127.0.1.1       PC-LAPTOP.localdomain            PC-LAPTOP
```

### Root 密码

```diff
passwd
```

输入并确认密码（密码没有回显，输完直接回车即可）。

### 安装基本软件包

安装基本软件包，使用 GRUB 为启动器：

```bash
pacman -S grub efibootmgr networkmanager network-manager-applet dialog wireless_tools wpa_supplicant os-prober mtools dosfstools ntfs-3g linux-headers reflector git sudo
```

编辑文件 grub：

```bash
vim /etc/default/grub
```

取消掉 GRUB_DISABLE_OS_PROBER=false 前的注释（#）。
再执行以下命令：

```bash
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=Arch
```

生成 grub.cfg：

```bash
grub-mkconfig -o /boot/grub/grub.cfg
```

![grub-mkconfig.png](https://img.imql.life/illustrations/84c7248e37454fc1007dd0464c9065e0.png)

## 重启

退出新系统：

```bash
exit
```

取消挂载：

```bash
umount -R /mnt
```

重启：

```bash
reboot
```

## 登入新系统

### 连接无线网

启动网络服务：

```bash
systemctl enable --now NetworkManager
```

设置 WiFi：

```bash
nmtui
```

### 创建个人用户并授权

创建用户 ql，创建家目录，加入 wheel 组，指定 shell：

```bash
useradd -m -G wheel -s /bin/bash ql
```

为用户 ql 设定密码：

```bash
passwd ql
```

编辑文件 sudoers：

```bash
EDITOR=vim visudo
```

取消掉`%wheel ALL=(ALL:ALL) NOPASSWD: ALL`前的注释（#）。

### 安装显卡驱动

我的电脑是 AMD 集显：

```bash
pacman -S xf86-video-amdgpu
```

### 安装 Display Server

我装的是开源世界最为流行的 xorg：

```bash
pacman -S xorg
```

出现选择直接回车即可。

### 安装 Display Manager

我装的是 KDE 的：

```bash
pacman -S sddm
```

设置开机自动启动：

```bash
systemctl enable sddm
```

### 安装 Desktop Environment

安装 KDE：

```bash
pacman -S plasma kde-applications packagekit-qt5
```

一路默认即可。

### 重启

```bash
reboot
```

以个人用户登录。

### 安装字体

英文字体：

```bash
sudo pacman -S ttf-dejavu ttf-droid ttf-hack ttf-font-awesome otf-font-awesome ttf-lato ttf-liberation ttf-linux-libertine ttf-opensans ttf-roboto ttf-ubuntu-font-family
```

中文字体：

```bash
sudo pacman -S ttf-hannom noto-fonts noto-fonts-extra noto-fonts-emoji noto-fonts-cjk adobe-source-code-pro-fonts adobe-source-sans-fonts adobe-source-serif-fonts adobe-source-han-sans-cn-fonts adobe-source-han-sans-hk-fonts adobe-source-han-sans-tw-fonts adobe-source-han-serif-cn-fonts wqy-zenhei wqy-microhei
```

### 系统语言

按 Win 键，搜索运行 language，添加简体中文（在最下方），调整其优先级到最上方，Apply（应用）：
![系统语言.png](https://img.imql.life/illustrations/08c27c0c494c4894355239b5da75681f.png)
注销重新登录以生效。

### 添加 archlinuxcn 源

编辑文件 pacman.conf：

```bash
sudo vim /etc/pacman.conf
```

文件末尾空一行追加以下内容（使用的北外的镜像站）。

```
[archlinuxcn]
Server = https://mirrors.bfsu.edu.cn/archlinuxcn/$arch
```

同步并安装 archlinuxcn-keyring：

```bash
sudo pacman -Sy && sudo pacman -S archlinuxcn-keyring
```

### 安装 yay

[yay](https://github.com/Jguer/yay) 是一个受欢迎的 [AUR](https://wiki.archlinux.org/title/Arch_User_Repository) 助手，执行以下命令安装。

```bash
sudo pacman -S yay
```

### 安装输入法[^3]

安装 fcitx、fcitx-im 和 fcitx-configtool：

```bash
sudo pacman -S fcitx fcitx-im fcitx-configtool
```

安装 [fcitx-sogoupinyin](https://aur.archlinux.org/packages/fcitx-sogoupinyin/)：

```bash
yay -S fcitx-sogoupinyin
```

一路回车即可。
创建文件 .pam_environment：

```bash
vim ~/.pam_environment
```

设置 IM 环境变量：

```
GTK_IM_MODULE DEFAULT=fcitx
QT_IM_MODULE  DEFAULT=fcitx
XMODIFIERS    DEFAULT=\@im=fcitx
```

注销重新登录，按 Win 键，搜索“Fcitx 配置”，回车运行，将位于第一个的“键盘 - 英语（美国）”删除，输入法即可正常使用了。

### 安装 Timeshift

当系统出现故障的时候，可以通过备份的快照来恢复系统。

```bash
sudo pacman -S timeshift
```

按 Win 键或者 Alt+Space，搜索运行 Timeshift。
快照类型一般选择 RSYNC：
![选择快照类型.png](https://img.imql.life/illustrations/63c1deb6f5662f20344d876d87f6b5af.png)
选择快照位置：
![选择快照位置.png](https://img.imql.life/illustrations/e1f73ba8c4128cd7cfc1dd59d3a9b28c.png)
选择快照等级：
![选择快照等级.png](https://img.imql.life/illustrations/00373ee1d29601e5854597831f847992.png)
默认是不备份用户目录，默认即可。
设置完成：
![设置完成.png](https://img.imql.life/illustrations/14d974905b3339cceb70866cadac1ff7.png)
启用并启动 [cron](<https://wiki.archlinux.org/title/Cron_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)>)：

```powershell
sudo systemctl enable --now cronie
```

### 安装 fish

```bash
sudo pacman -S fish
```

设定为默认 shell：

```bash
chsh -s /usr/bin/fish
```

注销重新登录以生效。

### 禁用休眠[^4]

编辑文件 sleep.conf：

```bash
vim /etc/systemd/sleep.conf
```

```diff
[Sleep]
#AllowSuspend=yes
-#AllowHibernation=yes
-#AllowSuspendThenHibernate=yes
-#AllowHybridSleep=yes
```

```diff
[Sleep]
#AllowSuspend=yes
+AllowHibernation=no
+AllowSuspendThenHibernate=no
+AllowHybridSleep=no
```

### 安装火狐浏览器

```bash
sudo pacman -S firefox
```

安装中文语言包：

```bash
sudo pacman -S firefox-i18n-zh-cn
```

## 美化启动项选择界面

每次重启电脑，如下图，默认的启动项选择界面看起来比较简朴，我们可以换一个主题。
![默认的启动项选择界面.png](https://img.imql.life/illustrations/b6c9b499166502f5ab2733698115dd6d.png)
[前往主题仓库](https://github.com/AdisonCavani/distro-grub-themes)，下载 Arch 主题文件：
![arch.png](https://img.imql.life/illustrations/9ed9aa73446cc14d3e785c38a4f71718.png)
安装 Grub Customizer：

```powershell
sudo pacman -S grub-customizer
```

按 Win 键或者 Alt+Space，搜索运行 Grub Customizer。
点击外观设置，设定分辨率为 1920x1080：
![自定义分辨率.png](https://img.imql.life/illustrations/f92cad978180676abcad444479c50ed3.png)
点击主题后面的加号，选择以上下载好的主题文件，点击左上角文件，保存：
![保存.png](https://img.imql.life/illustrations/3010e38e90ec4f52cd43ee26ea34a994.png)
重启，至此，Windows 11 和 Arch Linux 双系统安装园满完成。

## 参考

- [2021 Archlinux 双系统安装教程（超详细）](https://zhuanlan.zhihu.com/p/138951848)
- [Archlinux 安装教程超详细（2021.11.15）](https://zhuanlan.zhihu.com/p/433920079)
- [General recommendations](<https://wiki.archlinux.org/title/General_recommendations_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)>)

[^1]: [Dual boot with Windows](https://wiki.archlinux.org/title/Dual_boot_with_Windows)
[^2]: [UTC in Microsoft Windows](https://wiki.archlinux.org/title/System_time#UTC_in_Microsoft_Windows)
[^3]: [Fcitx](<https://wiki.archlinux.org/title/Fcitx_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)>)
[^4]: [Disabling suspend](https://wiki.archlinux.org/title/Power_management#Disabling_suspend)
