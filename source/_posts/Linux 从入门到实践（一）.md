---
title: Linux 从入门到实践（一）
urlname: autqc0
date: "2020-02-03 16:36:28"
updated: "2023-08-12 11:15:15"
trans: Linux_Learning_1
cover: "https://img.imql.life/Linux.jpg"
tags:
  - openEuler
  - VMware Workstation
categories:
  - Linux 从入门到实践
---

操作系统作为软件的软件，实在是重中之重。

<!-- more -->

## 搭建学习环境

### 安装 VMware

下载[学习版](https://www.52pojie.cn/thread-1026907-1-1.html)，安装步骤不多说了，只是有一点建议，也是我装软件的原则：能不装 C 盘就别装 C 盘。

### 下载系统映像

### 安装系统映像

1. VMware pro 15 安装完成后，启动，点击创建新的虚拟机；

![创建新的虚拟机.png](https://img.imql.life/illustrations/9b7ce21705bfd6a24278d49958b04155.png)

2. 选择典型，下一步；

![典型.png](https://img.imql.life/illustrations/94fb119b01d8f151a959257206833f7b.png)

3. 选择稍后安装操作系统，下一步；

![选择稍后安装操作系统.png](https://img.imql.life/illustrations/3f34c37ba95541e9b7fbc61b9c498517.png)

4. 客户机操作系统选择 Linux，版本选择其他 Linux 5.x 或更高版本内核 64 位，下一步；

![image.png](https://img.imql.life/illustrations/4b50e6b72986ed6843b83d6d4fe0f481.png)

5. 虚拟机名称和位置自定义，下一步；

![image.png](https://img.imql.life/illustrations/d77878a099831ba32ebd3940a3575dce.png)

6. 磁盘容量自定义。我这里就设为 60GB，下一步，完成；

![指定磁盘容量.png](https://img.imql.life/illustrations/504cfe03f47b8e03c108ff78627587d9.png)

7. 点击编辑此虚拟机，将内存设置为 4GB，处理器数量设为 4（一般为自己实体机处理器数量的一半）；

![image.png](https://img.imql.life/illustrations/47da15590f550014f7615d178196b944.png)

8. 点击 CD/DVD (IDE)，选择使用 ISO 映像文件，浏览，选择 openEuler 22.03 LTS 系统的 ISO 映像文件；
9. 点击网络适配器，选择桥接模式，即直接连接物理网络（实际网络），确定，开启此虚拟机，等待；
10. 回车以检查并开始安装；

![image.png](https://img.imql.life/illustrations/6b07f02b3b021e364a06292b59977081.png)

11. 选择中文，继续；

![image.png](https://img.imql.life/illustrations/6797bd8b78c71412d5449031339a4b89.png)

12. 点击安装目的地，点击完成，即自动分区即可；

![image.png](https://img.imql.life/illustrations/c2f7d189ffb11600fadc019214e20adf.png)

13. 点击软件选择，附加软件处勾选标准和开发工具，完成；

![image.png](https://img.imql.life/illustrations/2405c9dbba78750e2b928fab52c6cc78.png)

14. 点击网络和主机名；

![image.png](https://img.imql.life/illustrations/ac6841d48d3c406e28962f4d4f9076e6.png)

15. 开启以太网，不久就可看到当前自动获取到的 IP、默认路由（网关）和 DNS；

![image.png](https://img.imql.life/illustrations/9f5beeccf22d5bba5b6f13160e08f43c.png)

16. 点击配置，点击 IPv4 配置，选择方法为手动，点击添加，地址填上一步获取到的 IP 的以正斜杠分隔的前一部分，子网掩码填以正斜杠分隔的后一部分，网关即填以上获取到的默认路由，DNS 服务器填以上获取到的 DNS，保存；

![image.png](https://img.imql.life/illustrations/ddcea5d35b450cced0000d9aa053bc47.png)

17. 主机名修改为 openEuler，应用，完成；

![image.png](https://img.imql.life/illustrations/3406609ab132284d06ba4f96ea1dd891.png)

18. 点击根密码，为 root 用户设定密码；

![image.png](https://img.imql.life/illustrations/816b083f7419e1b30e41043e0d1f3fd5.png)

19. 开始安装，完毕后重启系统；

![image.png](https://img.imql.life/illustrations/276f53c45a2b2c0b51e63ff26570b42d.png)
