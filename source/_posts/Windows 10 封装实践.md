---
title: Windows 10 封装实践
urlname: amf5cr
date: "2021-08-29 15:40:25"
updated: "2023-08-12 11:15:15"
trans: The_Practice_of_Windows_10_Encapsulation
cover: "https://img.imql.life/Windows_10.jpeg"
tags:
  - 优启通
  - Easy Sysprep
  - Windows
  - VMware Workstation
categories:
  - PC
---

制作一个属于自己的操作系统镜像，想想就是一件很有意义的事情！

<!-- more -->

## 准备工作

1. 使用优启通制作 PE（选择生成 ISO 的制作方式）；

![生成ISO](https://img.imql.life/illustrations/ab9578864fe04b0991428e43c6cab603.png "生成ISO")

2. 准备一个 U 盘，将 Easy Sysprep5、Windows 10 (business edition) ISO 镜像和封装的软件放进去；
3. 安装 VMware pro 15。下载[学习版](https://www.52pojie.cn/thread-1026907-1-1.html)，安装步骤不多说了。

## 创建系统封装环境

1. 创建新的虚拟机；

![创建新的虚拟机](https://img.imql.life/illustrations/f848e367cb39d41907e0cdec5c6a0fb8.png "创建新的虚拟机")

2. 选择典型；

![典型](https://img.imql.life/illustrations/fdbbd160fa14f876b09a4cf53954ee88.png "典型")

3. 选择安装程序光盘映像文件(iso)，选择在准备工作中制作好的 ISO；

![安装程序光盘映像文件](https://img.imql.life/illustrations/7407030df93e801b00a22366e1575bb1.png "安装程序光盘映像文件")

4. 选择客户机操作系统，按图选择即可；

![选择客户机操作系统](https://img.imql.life/illustrations/9fa1d34992d5d69174446c19ca0d516b.png "选择客户机操作系统")

5. 命名虚拟机。注意默认虚拟机文件的存放位置是用户文件夹下，建议改到非 C 盘；

![命名虚拟机](https://img.imql.life/illustrations/a95e6ac3da4fbd28a3d1e45ab265697a.png "命名虚拟机")

6. 指定磁盘容量，考虑到会封装许多软件，容量调大些，比如 100G；

![指定磁盘容量](https://img.imql.life/illustrations/6ae8d8a0326de4d0827e74f0f7a30acb.png "指定磁盘容量")

7. 完成。

![完成](https://img.imql.life/illustrations/43639e80781b9c051723a090801814d9.png "完成")

## 安装 Windows 10

开启此虚拟机，意外发生了：
![意外发生了](https://img.imql.life/illustrations/9df2d0504e42aca52db109158687b897.png "意外发生了")
百度到了办法，先关一下机，点击编辑虚拟机设置，在高级中，固件类型选择 BIOS，确定，再开启虚拟机：
![固件类型](https://img.imql.life/illustrations/5f1d7b69b4695dc3691eaeb2b1374b96.png "固件类型")
选择第二个进入 PE：
![第二个](https://img.imql.life/illustrations/ac4dceb69070ad31f183283d043ae7e8.png "第二个")
挂载 U 盘，选择准备好的 U 盘，我这里显示的是已经挂载好了的状态：
![挂载U盘](https://img.imql.life/illustrations/978f2590503a9001f0c1bb93e080c672.png "挂载U盘")
桌面上，双击 DG 硬盘分区，选择 100G 的虚拟硬盘，即我们上面分配的，点击快速分区，设置成一个分区就行：
![快速分区](https://img.imql.life/illustrations/be78f84051e9b04ef95d6e73c15ac5ca.png "快速分区")
再双击桌面中的 EIX 系统安装，左侧已经自动识别到我们 U 盘上的镜像，选择 Windows 10 专业版，右侧则是刚刚创建的那个分区，单击选择上，点击一键恢复：
![EIX系统安装](https://img.imql.life/illustrations/7e56df19ac9491762d18dba33978e8cd.png "EIX系统安装")
这里将“恢复完成后自动运行万能驱动”勾掉，确认，等待重启：
![勾掉](https://img.imql.life/illustrations/ec174dbfb0529bdda0d3c2acd5bc93cb.png "勾掉")

## 进入审核模式

重启之后就到了这个熟悉的流程（OOBE）：
![OOBE](https://img.imql.life/illustrations/aeebdc8e9356d346ca64a7e275a233b3.png "OOBE")
不要着急点是，这里要按`Ctrl`+`Shift`+`F3`进入审核模式，刚进入是这样的：
![审核模式](https://img.imql.life/illustrations/c314b46361f31829113995a58571ad86.png "审核模式")
注意不要点确定，点了就又退回到 OOBE 了，这里点取消：
![取消](https://img.imql.life/illustrations/091c55bb3c6cd07f62381625b979b851.png "取消")

## 系统调整

1. 安装[图吧工具箱](https://pan.imql.life/PC/%E5%BF%85%E5%A4%87/%E5%9B%BE%E5%90%A7%E5%B7%A5%E5%85%B7%E7%AE%B1)；
2. 系统激活，这个就不多说了；
3. 系统更新；
4. 桌面图标设置。我习惯将“计算机”和“控制面板”显示出来；

![桌面图标设置.png](https://img.imql.life/illustrations/29bbad8eae0d02d7197f31a80a6a8a35.png)

5. 颜色偏爱设置。默认 Windows 模式改为浅色，透明效果打开，选择从我的背景自动选取一种主题色；

![颜色.png](https://img.imql.life/illustrations/438909f09b272910da69be93dbb48928.png)

6. 显示搜索图标。感觉搜索框太占地方了；

![显示搜索图标](https://img.imql.life/illustrations/796322da21fefa25863f20e04cc1c133.png "显示搜索图标")

7. 装上 Telnet 客户端。这样可以在 CMD 中使用`telnet`检测目标主机 TCP 端口是否开启；

![Telnet客户端.png](https://img.imql.life/illustrations/9221f04d76d71714659ac05ecea1a8ad.png)

8. 显示文件扩展名，这个必设；

![文件扩展名.png](https://img.imql.life/illustrations/ae57ed8954b6190968a0e9577801a913.png)

9. 最后使用 Dism++ 对系统进行优化。

![任务栏时钟精确到秒.png](https://img.imql.life/illustrations/500e590ebc88c017ecc5960ea6f94998.png)
![桌面壁纸质量调整.png](https://img.imql.life/illustrations/e09c672f3314f4f0a9a04f72c4a1671b.png)
![打开资源管理器时显示此电脑.png](https://img.imql.life/illustrations/17c97d5257e30f6f2db3644a81ebbe9a.png)
![最小化时显示完整路径.png](https://img.imql.life/illustrations/57d0a19cd8dbd1e7c7e2a0ec571162f3.png)

## 必装软件

1. [前往官网下载 Visual Studio Code](https://code.visualstudio.com/)，安装，建议勾上如图的选项；

![VScode.png](https://img.imql.life/illustrations/93c9fe7332e3d211e15f8a3ab2215c6a.png)

3. [前往官网下载微软电脑管家](https://pcmanager.microsoft.com/)，快速安装即可；
4. [前往官网下载 QQ](https://im.qq.com/pcqq)，立即安装即可；
5. [前往官网下载 Watt Toolkit](https://steampp.net/)，立即安装即可，推荐开启开机自启动；

![image.png](https://img.imql.life/illustrations/73e3b6697451cb46a6fed5ace20e3251.png)

6. [前往官网下载 WeGame 客户端](https://www.wegame.com.cn/)，立即安装即可；
7. [前往官网下载战网客户端](https://www.blizzardgames.cn/zh-cn/apps/battle.net/desktop)，安装，建议勾掉开机自启；
8. [前往官网下载 Epic Games 客户端](https://www.epicgames.com/site/zh-CN/home)，下一步即可；
9. [前往官网下载 Steam 客户端](https://store.steampowered.com/)，下一步即可。

## 系统清理

1. 卸载所有 Office 365 相关软件除了 OneDrive；

![image.png](https://img.imql.life/illustrations/61fc42379b473cc0ebf7622a60d97ad9.png)
![image.png](https://img.imql.life/illustrations/9949578ab4873568a9d8cb5c46cfd199.png)

2. 使用微软电脑管家清理优化下。

![image.png](https://img.imql.life/illustrations/7ba529df528b7429c47a1c9e97c85071.png)

## ES5 封装

运行 U 盘中的 Easy Sysprep5，点击设置，图中标记自定义即可，其他建议默认，点击封装、确定，等待上方提示完毕，重启进入 PE 执行第二阶段。
![自定义](https://img.imql.life/illustrations/97467a2f0fcc24e15f4f3f3c79e3bf9d.png "自定义")
重点来了！点击重启之后请不停按`F2`，直到进入 BIOS：
![进入BIOS](https://img.imql.life/illustrations/168f77860f007b9f0a7dbf142544f80f.png "进入BIOS")
重点没玩，左右键移动到“Boot”，然后让“CD-ROM Drive”往上移动两格，`F10`保存退出：
![调整启动顺序](https://img.imql.life/illustrations/9f7e53ace77a35acd3ff7ca2ef25ad3b.png "调整启动顺序")
还没完，`F10`保存退出后按两次回车，到这里也是选择第二个：
![第二个](https://img.imql.life/illustrations/837a5cd6eb6a369c6266edae31ac5672.png "第二个")
再次运行 Easy Sysprep5，点击设置，优化栏里全不勾选，不需要：
![全不勾选](https://img.imql.life/illustrations/4775d8dae786c58c59fbc236e4864547.png "全不勾选")
部署栏里，我按下图设置的，供参考。
![部署栏](https://img.imql.life/illustrations/a6cca17af3b10e0c8f3bc0926b8f20a5.png "部署栏")
系统栏里，我按下图设置的，供参考。
![系统栏](https://img.imql.life/illustrations/b460472421d3662aff519b5beef0e662.png "系统栏")
用户栏里，我按下图设置的，供参考。
![用户栏](https://img.imql.life/illustrations/b32019d14311704a2a8f8190c171dd09.png "用户栏")
其他栏中，有如图的注意，最后点击封装，确定，等待镜像备份完毕。
![其他栏](https://img.imql.life/illustrations/b15516504c127717d85fe60ab3ab37cc.png "其他栏")
镜像备份完毕后重启，不用进行任何操作，等待部署即可：
![部署](https://img.imql.life/illustrations/de9a6e1046ee9515a960bf28cc3af6f2.png "部署")
