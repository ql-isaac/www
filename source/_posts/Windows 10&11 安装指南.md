---
title: Windows 10&11 安装指南
urlname: cu2ro0
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
![Windows_10.png](https://img.imql.life/illustrations/4f492a33cd4965a5d79ef0955d09e1a3.png)

![Windows_11.png](https://img.imql.life/illustrations/4afb01eb459bc934a904d00ce5f8b196.png)
直接点击复制右边的下载链接（建议 BT），如果此时你的迅雷正在运行中的话，此时会自动解析种子并提示下载，如下图，速度还是很快的。
![速度很快.png](https://img.imql.life/illustrations/1e3e0006af3e1163e3efb51da8b152a7.png)
下载完成后勾选一下显示校验信息：
![Windows_10校验码.png](https://img.imql.life/illustrations/0affe41db723d3d076c2a29fbcfee04e.png)

![Windows_11校验码.png](https://img.imql.life/illustrations/d274140340fb886a6daa7db833633fe5.png)
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
![Windows_11安装要求.png](https://img.imql.life/illustrations/cc2f22885ce9760812246795263cb29f.png)
{% note info %}
直接安装 Windows 10/11 步骤一致，下面以 Windows 10 为例说明。
{% endnote %}
首先确保下载的镜像不在 C 盘，如果原来的操作系统是 Windows 7 之后的系统，直接双击打开镜像文件。
如果原来的操作系统为 Windwos 7，是不能直接双击打开镜像文件的，需要使用解压缩工具将镜像文件解压出来，例如使用 7z。
双击运行 setup.exe。
首先是提示你是否要对现在的镜像文件进行更新，建议这里选择更改 Windows 安装程序下载更新的方式：
![更改安装程序下载更新的方式.png](https://img.imql.life/illustrations/2691a7924eccaf0ca638c446e9ed872a.png)
选择不是现在，下一步（要是现在更新的话就需要等较长时间）：
![不是现在.png](https://img.imql.life/illustrations/2228cacfe2a310102146648fe3f92572.png)
检查准备中：
![检查准备中.png](https://img.imql.life/illustrations/e330eb0672b52e9248b2929017eb816c.png)
选择版本，我这里选择专业版：
![Windows_10专业版.png](https://img.imql.life/illustrations/9b47b8b9da3a3f508d2a6caf6d869ddf.png)
接受条款：
![接受条款.png](https://img.imql.life/illustrations/a2f561690cbabffa75b1d31fa6fba2e2.png)
最后的准备：
![最后的准备.png](https://img.imql.life/illustrations/16191682699f2492257dba03b352326c.png)
这里就默认保留个人文件和应用，也就是仅仅操作系统会被改变，C 盘中的个人文件和应用会被保留，可以自行更改要保留的内容。
![保留个人文件和应用.png](https://img.imql.life/illustrations/964e915ff11712a727062337655567bd.png)
{% note warning %}
升级跨度比较大的话这里只能保留 C 盘中的个人文件。
{% endnote %}
开始安装，等待即可。

## 方法二：从 U 盘启动安装

{% note success %}
适用情况：刚组装了一台台式机，还没有操作系统；电脑进不去了，C 盘没什么文件，可以直接格式化。
{% endnote %}
空 U 盘插入到一台正常使用的电脑上，使用 [Rufus](https://rufus.ie/) 制作启动盘：
![制作.png](https://img.imql.life/illustrations/6aea48e9b453b49b525b8d4bb93f7849.png)
在制作 Windows 11 安装 U 盘时，注意到镜像选项处有两个特别的选项，如下图，简单理解就是一个会去检查是否支持 TPM 2.0，一个不会。
![需要TPM2.0.png](https://img.imql.life/illustrations/3385906ad02d0aaa095dc1287a45e7bc.png)
![不需要TPM2.0.png](https://img.imql.life/illustrations/fb3e5abfa0edacb8e817f63764a8a619.png)
制作完成后就可以将安装盘插到要安装的机器上，启动电脑，同时不停按 F2 进入 BIOS，确认引导模式为 UEFI。
F10 保存退出 BIOS，同时不停按 F12 进入启动项选择界面。键盘上下键选择带“EFI”“USB”字样的，一般是第二个，回车。
下一步：
![下一步.png](https://img.imql.life/illustrations/cbd03453b8976de4629a99c0405333cc.png)
现在安装：
![现在安装.png](https://img.imql.life/illustrations/66ad6d7f443df4939e18449720fc6b86.png)
选择要安装的 Windows 10/11，我这里选择专业版：
![选择要安装的Windows_10.png](https://img.imql.life/illustrations/04ecf28931a9694cf7d7f2fc319077ef.png)
![选择要安装的Windows_11.png](https://img.imql.life/illustrations/44cf871b1470015c8d1700bb0cb44a6c.png)
接受：
![接受.png](https://img.imql.life/illustrations/24e9a7e38770bc91ae01c5115cf03d2c.png)
自定义安装：
![自定义安装.png](https://img.imql.life/illustrations/149abcb6b5d30fac48420c705810922d.png)
上图中如果选择升级安装，会有下面的提示。
![升级选项不可用.png](https://img.imql.life/illustrations/0fdafbcba9ada3b4dfd51fa6c905f5bc.png)
如果这是一台新机器，还没有安装操作系统，那么选择未分配空间的驱动器，选择新建，设定 C 盘大小，应用，确定：
{% note info %}
C 盘大小建议设定为 50-100GB。
{% endnote %}
![驱动器0.png](https://img.imql.life/illustrations/baf8e6365fdf4b06d6c782c41b79c0c3.png)
接着依次划分剩余的未分配空间给 D 盘、E 盘等盘。
如果这是一台旧机器，C 盘上安装过操作系统，但是 C 盘没什么文件，可以直接格式化，那么我们依次删除前三个驱动器分区：
![前三个驱动器分区.png](https://img.imql.life/illustrations/8505f97a0440ce80d8db19c80d169f7e.png)
![删除分区1.png](https://img.imql.life/illustrations/fe0e3457a04d4c7aa6749e2cb6f0d2ec.png)
![删除分区2.png](https://img.imql.life/illustrations/835cad69f583a35595825561f8c716c0.png)
![删除分区3.png](https://img.imql.life/illustrations/a5b9884fbcf6202d8a6448a090e657ca.png)
这里有可能只有两个驱动器分区需要删除：
![前两个驱动器分区.png](https://img.imql.life/illustrations/6c75cf646f2a5d5e35a8629d3f501db9.png)
接下来就和上述机器还没有安装操作系统的情况一样，选择未分配空间的驱动器，新建 C 盘、D 盘和 E 盘等盘。
选择新建的 C 盘（第一个类型为主分区的分区），下一步：
![下一步.png](https://img.imql.life/illustrations/e02e1698e397eca429a7b58fa08706ed.png)
安装中，等待即可：
![安装中.png](https://img.imql.life/illustrations/9b89164e9a836174b5ed2ecba60ed38c.png)

## 方法三：在 PE 中安装

{% note info %}
PE，即预安装环境，是带有有限服务的最小 Windows，在 PE 中安装 Windows 是最好的 Windows 安装办法。
{% endnote %}

### 制作 PE

首先需要一个 U 盘，最好容量大一下，这样可以放下多个镜像，许多其他软件，满足各种安装需要。制作 PE 的软件比较多，强烈推荐[微 PE](https://www.wepe.com.cn/) 和[优启通](https://www.upe.net/)，我这里以优启通为例。
运行优启通，选择磁盘，全新制作：
![优启通.png](https://img.imql.life/illustrations/59c81bca1d8655f335a86a6aa9672b78.png)
制作完成后就可以将 PE 盘插到要安装的机器上，启动电脑，同时不停按 F2 进入 BIOS，确认引导模式为 UEFI。
F10 保存退出 BIOS，同时不停按 F12 进入启动项选择界面。键盘上下键选择带“EFI”“USB”字样的，一般是第二个，回车。

### 备份 C 盘文件（可选）

看下自己的 C 盘有没有重要文件，一般就是桌面和下载中的文件，考虑转移一下。

### 硬盘分区（可选）

对于新的机器，或者整个硬盘数据可清除的情况，可通过桌面上的 DG 硬盘分区对硬盘分好区。
选择好硬盘，选择上方的快速分区，注意分区表类型选择 GUID，分区数目自定义，其他的推荐默认就好，确定：
![硬盘分区.png](https://img.imql.life/illustrations/029cdb1d2d876cd9bfef31fe3a4d5e43.png)

### 安装

可直接双击镜像文件安装，之后的步骤同从 U 盘启动安装，也可选择桌面上的 EIX 系统安装进行安装。
左侧选择版本，右侧选择系统盘（注意在 PE 中，系统盘不一定为 C 盘，请以实际系统盘盘符为准），点击一键恢复，确认：
![映像恢复.png](https://img.imql.life/illustrations/e758d8f09dd77849f717584cb7501028.png)
![确认.png](https://img.imql.life/illustrations/a9b33b1f88c7bd6d55f8378fb8422796.png)
恢复中，等待即可：
![恢复中.png](https://img.imql.life/illustrations/68727d4dde125f490731c14479a478f8.png)

## 开箱体验（OOBE）

OOBE（Out-of-box experience），即开箱体验，它是在安装完 Windows 后要做的第一件事，以下为 Windows 10/11 的演示。

### Windows 10

区域设置：
![中国-Windows10.png](https://img.imql.life/illustrations/636f11fbfb89df7a200a2b92831bcd31.png)
输入法：
![微软拼音-Windows10.png](https://img.imql.life/illustrations/f8a23fb85343e708d90578d6e2c1db03.png)
添加第二种键盘布局：
![跳过-Windows10.png](https://img.imql.life/illustrations/bd35ce68c412ee4892259d4601fefbbf.png)
连接到网络：
![我没有Internet连接-Windows10.png](https://img.imql.life/illustrations/5c6b490484d59323a0976ecd76fe13f1.png)
创建用户：
![创建用户-Windows10.png](https://img.imql.life/illustrations/ede5bc55603a1f2edd16b88467222dbd.png)
设置密码：
![设置密码-Windows10.png](https://img.imql.life/illustrations/80012c16a042425c5f33e73258b878f4.png)
隐私设置：
![隐私设置-Windows10.png](https://img.imql.life/illustrations/3a4159666f7c865f3f9f292c553d34b7.png)
微软小娜：
![微软小娜-Windows10.png](https://img.imql.life/illustrations/ee22686f9625f35d54d9cf4a54aaf1d0.png)
即将完毕：
![即将完毕-Windows10.png](https://img.imql.life/illustrations/2d2c4b4a076df19700550c3aa6ed0de9.png)

### Windows 11

区域设置：
![中国-Windows11.png](https://img.imql.life/illustrations/879a8b90862a7faff41b039465cf284d.png)
输入法：
![微软拼音-Windows11.png](https://img.imql.life/illustrations/48589410744e3f64b74e2ec561aebbc7.png)
添加第二种键盘布局：
![跳过-Windows11.png](https://img.imql.life/illustrations/f59062d113ced36eb48b81ede44fed9c.png)
连接到网络：
![我没有Internet连接-Windows11.png](https://img.imql.life/illustrations/ecf65979b73b2cc241bcbc2164fc1c91.png)
创建用户：
![创建用户-Windows11.png](https://img.imql.life/illustrations/16c2362c562f02be73d8c2bf7ac06755.png)
设置密码：
![设置密码-Windows11.png](https://img.imql.life/illustrations/ce308ded8ccab4749155e9afcec5cdff.png)
隐私设置：
![隐私设置-Windows11.png](https://img.imql.life/illustrations/87c952585eb17fa9da1a90659b098e5b.png)
即将完毕：
![即将完毕-Windows11.png](https://img.imql.life/illustrations/fb2d5aaadd76b64678e7cba22445e38a.png)
