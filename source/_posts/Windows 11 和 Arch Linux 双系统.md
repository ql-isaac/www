---

title: Arch Linux 和 Windows 11 双系统

trans: Dual_Booting_Windows_11_and_Arch_Linux

date: 2022-04-30 21:51:00

updated: 2022-04-30 21:51:00

cover: https://img.imql.life/Dual_Booting_Windows_11_and_Arch_Linux.png

tags:

- Arch Linux
- Windows 11 专业版

categories:

- PC

---

还不会安装 Linux？快点进来！

<!-- more -->

## 下载系统镜像

[前往官方下载地址](https://archlinux.org/download/)，我使用的 HTTP 下载：

![HTTP下载.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652623598853-a5907027-58e3-4525-a8ee-ea5f3b088f87.png#clientId=u35401e7e-9e63-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uc844e9aa&name=HTTP%E4%B8%8B%E8%BD%BD.png&originHeight=940&originWidth=773&originalType=binary&ratio=1&rotation=0&showTitle=false&size=29801&status=done&style=stroke&taskId=u5ec73399-cdec-44e5-92a4-95d555d4c6d&title=)

## 磁盘管理

使用 Windows 的磁盘管理从 D 盘分 170GB 空闲空间出来，如下图。

![170GB.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651469771843-f144b5af-6010-4744-bc60-664705eb0137.png#clientId=u7e02456c-a30b-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u04c797f5&name=170GB.png&originHeight=535&originWidth=1423&originalType=binary&ratio=1&rotation=0&showTitle=false&size=46082&status=done&style=stroke&taskId=u5830cf6a-6209-4672-b1eb-da95b1a548c&title=)

## 制作启动盘

空 U 盘插入电脑，如下图，使用 [Rufus](https://rufus.ie/) 制作，注意分区类型为 GPT 而非默认的 MBR，写入方式为推荐的 ISO。

![制作.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651462348362-7165685a-1701-4aba-adbb-b174756229d9.png#clientId=u7e02456c-a30b-4&crop=0&crop=0&crop=1&crop=1&from=drop&height=753&id=u472472f2&name=%E5%88%B6%E4%BD%9C.png&originHeight=753&originWidth=478&originalType=binary&ratio=1&rotation=0&showTitle=false&size=30299&status=done&style=stroke&taskId=u4aa932c0-aefd-4c8e-988b-555eb22d55a&title=&width=478)

![以ISO镜像模式写入.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651462411464-60223979-3169-4860-91f6-3c293c64a525.png#clientId=u7e02456c-a30b-4&crop=0.0032&crop=0.0028&crop=1&crop=1&from=drop&height=355&id=ue75ea86d&name=%E4%BB%A5ISO%E9%95%9C%E5%83%8F%E6%A8%A1%E5%BC%8F%E5%86%99%E5%85%A5.png&originHeight=356&originWidth=625&originalType=binary&ratio=1&rotation=0&showTitle=false&size=30009&status=done&style=stroke&taskId=uf078ca91-6013-4ffa-a1f5-68bd4ba3281&title=&width=623)

## 禁用快速启动和休眠[[1]](#参考)

![禁用快速启动和休眠.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651471538641-d44d1719-69f4-429f-9c6d-9221f756168e.png#clientId=u7e02456c-a30b-4&crop=0.004&crop=0&crop=0.9946&crop=0.9873&from=drop&height=743&id=u385ed2f2&name=%E7%A6%81%E7%94%A8%E5%BF%AB%E9%80%9F%E5%90%AF%E5%8A%A8%E5%92%8C%E4%BC%91%E7%9C%A0.png&originHeight=750&originWidth=1424&originalType=binary&ratio=1&rotation=0&showTitle=false&size=55773&status=done&style=stroke&taskId=ue62d35da-0770-4661-813f-ce29379a110&title=&width=1411)

## 时间表示标准统一[[2]](#参考)

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

![正式开始安装.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652592105770-ec45b777-d680-4c5f-82b6-a4917b2dba64.png#clientId=ufbaa7256-80d6-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u5422b3ac&name=%E6%AD%A3%E5%BC%8F%E5%BC%80%E5%A7%8B%E5%AE%89%E8%A3%85.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16909&status=done&style=stroke&taskId=u936927df-cf59-4eff-bb05-4aa4979c538&title=)

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

![剩下的138GB.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651474371101-ce3dc793-1147-4b20-8bf7-90830d7b6e2f.png#clientId=u96a8fb3b-ff30-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ucc7cf5a0&name=%E5%89%A9%E4%B8%8B%E7%9A%84138GB.png&originHeight=980&originWidth=956&originalType=binary&ratio=1&rotation=0&showTitle=false&size=48904&status=done&style=stroke&taskId=u8d128bbb-59b8-4b73-bcf3-e87d36d8d49&title=)

选择 New，给交换分区分配 3GB，选择 Type，设定分区类型为 Linux swap，如下图。

![Linux_swap.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651475147666-3bbb8da3-fedb-4b0a-a353-0b365ee41783.png#clientId=u96a8fb3b-ff30-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u569f997b&name=Linux_swap.png&originHeight=971&originWidth=956&originalType=binary&ratio=1&rotation=0&showTitle=false&size=577144&status=done&style=stroke&taskId=uca7e7cb1-a2ae-415e-8b0b-87ece8798c3&title=)

选择剩下的 135GB，选择 New，给家分区分配剩下的空间，选择 Type，设定分区类型为 Linux home，如下图。

![Linux_home.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651475595065-4b277020-05ce-4dc6-861e-4858bce4e650.png#clientId=u96a8fb3b-ff30-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u9a14bdd9&name=Linux_home.png&originHeight=976&originWidth=956&originalType=binary&ratio=1&rotation=0&showTitle=false&size=867633&status=done&style=stroke&taskId=ua6fd2de6-6cad-443b-be11-e4c0d9c4d18&title=)

选择 Write，输入 yes 回车：

![Write.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651475696486-b78de1a5-8e42-4ccb-b926-fcaf6a5f684b.png#clientId=u96a8fb3b-ff30-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u65cb63e6&name=Write.png&originHeight=980&originWidth=958&originalType=binary&ratio=1&rotation=0&showTitle=false&size=608606&status=done&style=stroke&taskId=u91a08809-4c4e-46da-9736-1f3b4e701d3&title=)

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

创建 [locale.conf(5)](https://man.archlinux.org/man/locale.conf.5) 文件，并 [编辑设定 LANG 变量](<https://wiki.archlinux.org/title/Locale_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)#%E7%B3%BB%E7%BB%9F%E5%8C%BA%E5%9F%9F%E8%AE%BE%E7%BD%AE>)：

```bash
vim /etc/locale.conf
```

```bash
LANG=en_US.UTF-8
```

### 网络

创建文件 hostname，即自定义设定主机名：

```bash
vim /etc/hostname
```

```bash
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

![grub-mkconfig.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651484064808-829e80f0-6fe9-42d2-935e-27e30b8d86cf.png#clientId=u418953c8-9fbc-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uad577de9&name=grub-mkconfig.png&originHeight=343&originWidth=958&originalType=binary&ratio=1&rotation=0&showTitle=false&size=217648&status=done&style=stroke&taskId=u8c1a8af4-9d70-4518-beeb-d02116b70d2&title=)

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

![系统语言.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652716174557-b71999bb-a0c4-410e-9c37-f044c0b34d4c.png#clientId=uef7f94a1-6f8d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u626f24f2&name=%E7%B3%BB%E7%BB%9F%E8%AF%AD%E8%A8%80.png&originHeight=729&originWidth=1019&originalType=binary&ratio=1&rotation=0&showTitle=false&size=39865&status=done&style=stroke&taskId=u48e34b15-9fde-4cb1-8ca3-ffbb56ff717&title=)

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

### 安装输入法[[3]](#参考)

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

![选择快照类型.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651577906559-d6a3901b-30b5-4206-a6e4-b01eb74bbc4e.png#clientId=ubce10013-ef14-4&crop=0.1112&crop=0.082&crop=0.8889&crop=0.8811&from=drop&height=679&id=u5fc297a3&name=%E9%80%89%E6%8B%A9%E5%BF%AB%E7%85%A7%E7%B1%BB%E5%9E%8B.png&originHeight=873&originWidth=774&originalType=binary&ratio=1&rotation=0&showTitle=false&size=42184&status=done&style=stroke&taskId=ufa4998c0-cb83-4d90-b7a5-813f8819d84&title=&width=602)

选择快照位置：

![选择快照位置.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651578206793-6db7d977-bfda-4732-9f5c-189a0708b7bd.png#clientId=ubce10013-ef14-4&crop=0.1113&crop=0.0808&crop=0.8887&crop=0.8847&from=drop&height=679&id=u82692c21&name=%E9%80%89%E6%8B%A9%E5%BF%AB%E7%85%A7%E4%BD%8D%E7%BD%AE.png&originHeight=873&originWidth=774&originalType=binary&ratio=1&rotation=0&showTitle=false&size=105772&status=done&style=stroke&taskId=u32455747-024b-4158-a263-f1cb85e5598&title=&width=602)

选择快照等级：

![选择快照等级.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651578615513-77328040-0cce-4cb5-b8d7-781f7b7da912.png#clientId=ubce10013-ef14-4&crop=0.1113&crop=0.0832&crop=0.8888&crop=0.8823&from=drop&height=679&id=u7b193b0a&name=%E9%80%89%E6%8B%A9%E5%BF%AB%E7%85%A7%E7%AD%89%E7%BA%A7.png&originHeight=873&originWidth=774&originalType=binary&ratio=1&rotation=0&showTitle=false&size=122419&status=done&style=stroke&taskId=u04ec1286-6027-4af0-9363-c6b1fbfb8d6&title=&width=602)

默认是不备份用户目录，默认即可。

设置完成：

![设置完成.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651579200524-0cd722d5-f8c4-4f37-8629-aee8b40cccd8.png#clientId=ubce10013-ef14-4&crop=0.1019&crop=0.0773&crop=0.8995&crop=0.8873&from=drop&height=726&id=uc6c83ece&name=%E8%AE%BE%E7%BD%AE%E5%AE%8C%E6%88%90.png&originHeight=910&originWidth=860&originalType=binary&ratio=1&rotation=0&showTitle=false&size=166361&status=done&style=stroke&taskId=u03cb84a7-69a2-4058-8f08-6617b98e16b&title=&width=686)

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

### 禁用休眠[[4]](#参考)

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

![默认的启动项选择界面.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652628421134-30b74ced-683a-40a1-9c55-e97fc7ea4a61.png#clientId=ue72cc7c5-5300-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u60e96644&name=%E9%BB%98%E8%AE%A4%E7%9A%84%E5%90%AF%E5%8A%A8%E9%A1%B9%E9%80%89%E6%8B%A9%E7%95%8C%E9%9D%A2.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11513&status=done&style=stroke&taskId=u428510d5-536d-4643-9146-d32ba8076f5&title=)

[前往主题仓库](https://github.com/AdisonCavani/distro-grub-themes)，下载 Arch 主题文件：

![arch.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652717311758-9a775c23-7abb-4e7d-9832-4cac8788304c.png#clientId=uef7f94a1-6f8d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u0cec2f24&name=arch.png&originHeight=630&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28283&status=done&style=stroke&taskId=u2eae46fb-04ac-44a5-aa08-60e2c716683&title=)

安装 Grub Customizer：

```powershell
sudo pacman -S grub-customizer
```

按 Win 键或者 Alt+Space，搜索运行 Grub Customizer。

点击外观设置，设定分辨率为 1920x1080：

![自定义分辨率.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652716681627-a3c993c9-91cb-4809-a6f9-660fe19b7d36.png#clientId=uef7f94a1-6f8d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uff37b535&name=%E8%87%AA%E5%AE%9A%E4%B9%89%E5%88%86%E8%BE%A8%E7%8E%87.png&originHeight=629&originWidth=899&originalType=binary&ratio=1&rotation=0&showTitle=false&size=62679&status=done&style=stroke&taskId=u8d97fd4d-3185-470e-a8ca-4ed5bc2abc5&title=)

点击主题后面的加号，选择以上下载好的主题文件，点击左上角文件，保存：

![保存.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652717709948-d0a76ea0-3410-462a-b25f-e84eeef13f66.png#clientId=uef7f94a1-6f8d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u15f32a17&name=%E4%BF%9D%E5%AD%98.png&originHeight=628&originWidth=898&originalType=binary&ratio=1&rotation=0&showTitle=false&size=66400&status=done&style=stroke&taskId=u5a5ca3e7-75d9-46b8-844e-dccfad6bb1a&title=)

重启，至此，Windows 11 和 Arch Linux 双系统安装园满完成。

## 参考

1. [Dual boot with Windows](https://wiki.archlinux.org/title/Dual_boot_with_Windows)[↩](#禁用快速启动和休眠-1)
2. [UTC in Microsoft Windows](https://wiki.archlinux.org/title/System_time#UTC_in_Microsoft_Windows)[↩](#时间表示标准统一-2)
3. [Fcitx](<https://wiki.archlinux.org/title/Fcitx_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)>)[↩](#安装输入法-3)
4. [Disabling suspend](https://wiki.archlinux.org/title/Power_management#Disabling_suspend)[↩](#禁用休眠-4)

- [2021 Archlinux 双系统安装教程（超详细）](https://zhuanlan.zhihu.com/p/138951848)
- [Archlinux 安装教程超详细（2021.11.15）](https://zhuanlan.zhihu.com/p/433920079)
- [General recommendations](<https://wiki.archlinux.org/title/General_recommendations_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)>)
