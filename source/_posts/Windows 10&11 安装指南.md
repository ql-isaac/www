---
title: Windows 10&11 安装指南
urlname: cu2ro0
author: ql-isaac
date: "2022-04-20 19:42:00"
updated: "2022-04-20 19:42:00"
trans: The_Installation_Guide_of_Windows_10_and_Windows_11
cover: "https://img.imql.life/The_Installation_Guide_of_Windows_10_and_Windows_11.png"
top_img: false
tags:
  - Windows
categories:
  - PC
---

还不会安装 Windows？快点进来！

<!-- more -->

## 下载系统镜像

两个下载渠道：[微软官网](https://www.microsoft.com/zh-cn/software-download)和 [I Tell You（新版）](https://next.itellyou.cn)，推荐 I Tell You （新版），这是一个提供原版软件下载链接的网站，下载工具的话就推荐[迅雷](https://www.xunlei.com/index.html)。我选择的 Windows 10 和 Window 11 镜像分别为：
![Windows_10.png](https://img.imql.life/illustrations/FuwRk74WuLIglu6XRXhaFfxsNStJ.png)

![Windows_11.png](https://img.imql.life/illustrations/Fphp_bjBreSmWCubeuNH-r79v1z_.png)
直接点击复制右边的下载链接（建议 BT），如果此时你的迅雷正在运行中的话，此时会自动解析种子并提示下载，如下图，速度还是很快的。
![速度很快.png](https://img.imql.life/illustrations/FuUsad4ZjV4GWmlYTCiMtnnttv-6.png)
下载完成后勾选一下显示校验信息：
![Windows_10校验码.png](https://img.imql.life/illustrations/FmYRXEehwJ21vTwk9Hi3CKT5ZFC6.png)

![Windows_11校验码.png](https://img.imql.life/illustrations/Fh_kPZRJ9Tf8FlzxL4U3-OJbioBc.png)
使用软件帮忙生成系统镜像的校验码（MD5、SHA1 和 SHA256 任选一个类型），我这里就直接使用 Windows 自带的命令来生成 SHA256 校验码：

```powershell
certutil.exe -hashfile .\zh-cn_windows_10_business_editions_version_21h2_updated_april_2022_x64_dvd_b0024895.iso SHA256
```

```
SHA256 hash of .\zh-cn_windows_10_business_editions_version_21h2_updated_april_2022_x64_dvd_b0024895.iso:
c0dd1ec3bfd04bcc1b69bfaa988e418caf594287c2ca52d291cb63f01df273ff
CertUtil: -hashfile command completed successfully.
```

```powershell
certutil.exe -hashfile .\zh-cn_windows_11_business_editions_updated_april_2022_x64_dvd_dec0b963.iso SHA256
```

```
SHA256 hash of .\zh-cn_windows_11_business_editions_updated_april_2022_x64_dvd_dec0b963.iso:
828ce37ed9c1c07002b865f00580a6a44b759ebfcbb83afb484da88fd7c6ef9d
CertUtil: -hashfile command completed successfully.
```

{% note info %}
注意系统镜像路径，我这里是在迅雷下载文件夹下进入 Windows Powershell 执行的。
{% endnote %}
将生成的校验码和图中的进行比对，完全一致则表明系统镜像未损坏。

## 方法一：直接安装

{% note success %}
适用情况：电脑比较卡；希望从 Windows 7、Windows 8 或 Windows 8.1 升级到 Windows 10/11。
{% endnote %}
Windows 11 安装要求较为严苛，如下图，请在安装前确认机器满足要求。
![Windows_11安装要求.png](https://img.imql.life/illustrations/FmMj01vkVKkpERIQIkkZgLn3PEzS.png)
{% note info %}
直接安装 Windows 10/11 步骤一致，下面以 Windows 10 为例说明。
{% endnote %}
首先确保下载的镜像不在 C 盘，如果原来的操作系统是 Windows 7 之后的系统，直接双击打开镜像文件。
如果原来的操作系统为 Windwos 7，是不能直接双击打开镜像文件的，需要使用解压缩工具将镜像文件解压出来，例如使用 7z。
双击运行 setup.exe。
首先是提示你是否要对现在的镜像文件进行更新，建议这里选择更改 Windows 安装程序下载更新的方式：
![更改安装程序下载更新的方式.png](https://img.imql.life/illustrations/FohgnTFkOYTTCPGfETO_3hsTuJbX.png)
选择不是现在，下一步（要是现在更新的话就需要等较长时间）：
![不是现在.png](https://img.imql.life/illustrations/FlLUA92Li5pWgTA8rTlKUTQ65g-N.png)
检查准备中：
![检查准备中.png](https://img.imql.life/illustrations/FjLuRsGtbm807Gz66ZJ8wEhg-qQW.png)
选择版本，我这里选择专业版：
![Windows_10专业版.png](https://img.imql.life/illustrations/Fk6ZBxtp8Kg9ViB5aQ5Z6bUibrun.png)
接受条款：
![接受条款.png](https://img.imql.life/illustrations/Fjw5QvKgsqRMOq9GnAI-0lwYGQy9.png)
最后的准备：
![最后的准备.png](https://img.imql.life/illustrations/FsQBvEpE5zdMAirJZwFvd31lq_PK.png)
这里就默认保留个人文件和应用，也就是仅仅操作系统会被改变，C 盘中的个人文件和应用会被保留，可以自行更改要保留的内容。
![保留个人文件和应用.png](https://img.imql.life/illustrations/Fv04n_0tdmarbusFoioeezWX99ax.png)
{% note warning %}
升级跨度比较大的话这里只能保留 C 盘中的个人文件。
{% endnote %}
开始安装，等待即可。

## 方法二：从 U 盘启动安装

{% note success %}
适用情况：刚组装了一台台式机，还没有操作系统；电脑进不去了，C 盘没什么文件，可以直接格式化。
{% endnote %}
空 U 盘插入到一台正常使用的电脑上，使用 [Rufus](https://rufus.ie/) 制作启动盘：
![制作.png](https://img.imql.life/illustrations/FuuYd3UJ5Hl1b1ziotwhzSWa3iV-.png)
在制作 Windows 11 安装 U 盘时，注意到镜像选项处有两个特别的选项，如下图，简单理解就是一个会去检查是否支持 TPM 2.0，一个不会。
![需要TPM2.0.png](https://img.imql.life/illustrations/FuOhLLsUygMeM03G1JEIThvT2Yav.png)
![不需要TPM2.0.png](https://img.imql.life/illustrations/FqLjWfD_0fS5U8aybHTd4wu0T3tg.png)
制作完成后就可以将安装盘插到要安装的机器上，启动电脑，同时不停按 F2 进入 BIOS，确认引导模式为 UEFI。
F10 保存退出 BIOS，同时不停按 F12 进入启动项选择界面。键盘上下键选择带“EFI”“USB”字样的，一般是第二个，回车。
下一步：
![下一步.png](https://img.imql.life/illustrations/FluACC3lpN07Wo0KXEFARB0WnlRd.png)
现在安装：
![现在安装.png](https://img.imql.life/illustrations/FiORizdMCsBJkpZlCyVSAHYI3mUH.png)
选择要安装的 Windows 10/11，我这里选择专业版：
![选择要安装的Windows_10.png](https://img.imql.life/illustrations/Fo14a6lCM1fKJvy4Pg5LqNT_qEVy.png)
![选择要安装的Windows_11.png](https://img.imql.life/illustrations/FsGsUo5fqLmLuB9NXiZMHGhiAHL0.png)
接受：
![接受.png](https://img.imql.life/illustrations/Fg0A9qlgSHNQ620n0_snrr2b75CK.png)
自定义安装：
![自定义安装.png](https://img.imql.life/illustrations/FjmZfqzLc-DePGjs7Vecs5LUxAe6.png)
上图中如果选择升级安装，会有下面的提示。
![升级选项不可用.png](https://img.imql.life/illustrations/FjVdsjqMEAGME2BPVl4lGZGjYoz_.png)
如果这是一台新机器，还没有安装操作系统，那么选择未分配空间的驱动器，选择新建，设定 C 盘大小，应用，确定：
{% note info %}
C 盘大小建议设定为 50-100GB。
{% endnote %}
![驱动器0.png](https://img.imql.life/illustrations/Fv7ItwhOiMyHUYC9dT_-kOm0dtP-.png)
接着依次划分剩余的未分配空间给 D 盘、E 盘等盘。
如果这是一台旧机器，C 盘上安装过操作系统，但是 C 盘没什么文件，可以直接格式化，那么我们依次删除前三个驱动器分区：
![前三个驱动器分区.png](https://img.imql.life/illustrations/Fk5GCDRZYa0iwGr08flHceabXUzW.png)
![删除分区1.png](https://img.imql.life/illustrations/Fscx8J0LADnAmCE3zi2EtUNOXaLd.png)
![删除分区2.png](https://img.imql.life/illustrations/FlxCLealJof7BN1b6GOUzVxPABJT.png)
![删除分区3.png](https://img.imql.life/illustrations/Fqqu9_S_LJLisNNSTOZvAaWaSfZv.png)
这里有可能只有两个驱动器分区需要删除：
![前两个驱动器分区.png](https://img.imql.life/illustrations/FkKSIF3svio4huWrdyYMnO88g-j2.png)
接下来就和上述机器还没有安装操作系统的情况一样，选择未分配空间的驱动器，新建 C 盘、D 盘和 E 盘等盘。
选择新建的 C 盘（第一个类型为主分区的分区），下一步：
![下一步.png](https://img.imql.life/illustrations/FuXunKZ6uG4gI_8gWanxn2Cmv_oc.png)
安装中，等待即可：
![安装中.png](https://img.imql.life/illustrations/FnHDWQDQhS4WoScm-gqkV3c5xs4g.png)

## 方法三：在 PE 中安装

{% note info %}
PE，即预安装环境，是带有有限服务的最小 Windows，在 PE 中安装 Windows 是最好的 Windows 安装办法。
{% endnote %}

### 制作 PE

首先需要一个 U 盘，最好容量大一下，这样可以放下多个镜像，许多其他软件，满足各种安装需要。制作 PE 的软件比较多，强烈推荐[微 PE](https://www.wepe.com.cn/) 和[优启通](https://www.upe.net/)，我这里以优启通为例。
运行优启通，选择磁盘，全新制作：
![优启通.png](https://img.imql.life/illustrations/Fg-S43GrwCRb7iOM2uyN2k_yyMUs.png)
制作完成后就可以将 PE 盘插到要安装的机器上，启动电脑，同时不停按 F2 进入 BIOS，确认引导模式为 UEFI。
F10 保存退出 BIOS，同时不停按 F12 进入启动项选择界面。键盘上下键选择带“EFI”“USB”字样的，一般是第二个，回车。

### 备份 C 盘文件（可选）

看下自己的 C 盘有没有重要文件，一般就是桌面和下载中的文件，考虑转移一下。

### 硬盘分区（可选）

对于新的机器，或者整个硬盘数据可清除的情况，可通过桌面上的 DG 硬盘分区对硬盘分好区。
选择好硬盘，选择上方的快速分区，注意分区表类型选择 GUID，分区数目自定义，其他的推荐默认就好，确定：
![硬盘分区.png](https://img.imql.life/illustrations/Fu-QL4TdaW-XK3qXsKIbUixrTzaz.png)

### 安装

可直接双击镜像文件安装，之后的步骤同从 U 盘启动安装，也可选择桌面上的 EIX 系统安装进行安装。
左侧选择版本，右侧选择系统盘（注意在 PE 中，系统盘不一定为 C 盘，请以实际系统盘盘符为准），点击一键恢复，确认：
![映像恢复.png](https://img.imql.life/illustrations/FmJSTGEL2n27fRxOzI55dOj1XnKC.png)
![确认.png](https://img.imql.life/illustrations/FqUCd6Nb2N6TpJvvleJjyIwsfYJe.png)
恢复中，等待即可：
![恢复中.png](https://img.imql.life/illustrations/FmRwgmfFGsPIT-NV8jbMtYf6bryJ.png)

## 开箱体验（OOBE）

OOBE（Out-of-box experience），即开箱体验，它是在安装完 Windows 后要做的第一件事，以下为 Windows 10/11 的演示。

### Windows 10

区域设置：
![中国-Windows10.png](https://img.imql.life/illustrations/FhT_Nli-ghCUzanpp-RUeMut3HGZ.png)
输入法：
![微软拼音-Windows10.png](https://img.imql.life/illustrations/FvI3R9S4u_baw1ofdb-yn6LpJRO7.png)
添加第二种键盘布局：
![跳过-Windows10.png](https://img.imql.life/illustrations/FuP2J8aVxBoi1MXrHB6J24TNcj6i.png)
连接到网络：
![我没有Internet连接-Windows10.png](https://img.imql.life/illustrations/FmL-3WA4zTsrIwac5rTTWjKiskbY.png)
创建用户：
![创建用户-Windows10.png](https://img.imql.life/illustrations/Ft8phQJAV1skWrro9z_KCr27nuGD.png)
设置密码：
![设置密码-Windows10.png](https://img.imql.life/illustrations/Fl3BMyOCa5Ln6R4UJdQGEJjOiQFJ.png)
隐私设置：
![隐私设置-Windows10.png](https://img.imql.life/illustrations/FpWLg53oV8RVZuRYC0bdZNFjoMv3.png)
微软小娜：
![微软小娜-Windows10.png](https://img.imql.life/illustrations/Fg_2YsbMPJWpXZV76cuW7Prz-__3.png)
即将完毕：
![即将完毕-Windows10.png](https://img.imql.life/illustrations/FgxwbDnHqn66yqq3ImdviCfvPl-r.png)

### Windows 11

区域设置：
![中国-Windows11.png](https://img.imql.life/illustrations/Fjws51GLghHunMAK9VYKQOak0nof.png)
输入法：
![微软拼音-Windows11.png](https://img.imql.life/illustrations/FvUeNZslBghwnWzsDVf1-e62Ubpw.png)
添加第二种键盘布局：
![跳过-Windows11.png](https://img.imql.life/illustrations/FkwbpHipcfxvdYmj1CtYOKTr-BHA.png)
连接到网络：
![我没有Internet连接-Windows11.png](https://img.imql.life/illustrations/FprThgy4_I_AbBXrumN7Y6oBX-ls.png)
创建用户：
![创建用户-Windows11.png](https://img.imql.life/illustrations/FjPnNHb2mUPaJ-gxgY2HfQ8ZZ_Og.png)
设置密码：
![设置密码-Windows11.png](https://img.imql.life/illustrations/Fj-ZRxGciqCXbxFRxaSywZIIQYqf.png)
隐私设置：
![隐私设置-Windows11.png](https://img.imql.life/illustrations/Fviz3BR04jdklDKfwNhSID4iHyn2.png)
即将完毕：
![即将完毕-Windows11.png](https://img.imql.life/illustrations/FnxiWodWjQnRtXZx8sedtd4eaWqo.png)
