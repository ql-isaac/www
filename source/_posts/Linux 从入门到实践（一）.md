---

title: Linux 从入门到实践（一）

trans: Linux_Learning_1

date: 2020-02-03 16:36:28

cover: https://img.imql.life/Linux.jpg

tags:

- openEuler 22.03 LTS
- VMware® Workstation 15 Pro

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

![](https://img.imql.life/illustrations/FgdRlL67rlGMC-7iTc7AIGOPGSOl.png)

2. 选择典型，下一步；

![](https://img.imql.life/illustrations/FtuvsocoNkG7jCDF7s1htnuTHTNW.png)

3. 选择稍后安装操作系统，下一步；

![](https://img.imql.life/illustrations/Fr45RcoMPoajeMw5oFc8bC2EpxiQ.png)

4. 客户机操作系统选择 Linux，版本选择其他 Linux 5.x 或更高版本内核 64 位，下一步；

![](https://img.imql.life/illustrations/Ftnig3TPaPo9ruNgAeWsccKMQMmU.png)

5. 虚拟机名称和位置自定义，下一步；

![](https://img.imql.life/illustrations/Fttj3QY4sPt0ex3VLX7r9xj56WQV.png)

6. 磁盘容量自定义。我这里就设为 60GB，下一步，完成；

![](https://img.imql.life/illustrations/FmhDAyMZCSoqrg0Lfwel2JSO4WR5.png)

7. 点击编辑此虚拟机，将内存设置为 4GB，处理器数量设为 4（一般为自己实体机处理器数量的一半）；

![](https://img.imql.life/illustrations/FqdsDRYbPphda6R_tfGDnp1_aaNm.png)

8. 点击 CD/DVD (IDE)，选择使用 ISO 映像文件，浏览，选择 openEuler 22.03 LTS 系统的 ISO 映像文件；
9. 点击网络适配器，选择桥接模式，即直接连接物理网络（实际网络），确定，开启此虚拟机，等待；
10. 回车以检查并开始安装；

![](https://img.imql.life/illustrations/FicJnFKIhh82Zgg1hWHwDVyza8We.png)

11. 选择中文，继续；

![](https://img.imql.life/illustrations/FndzCHpxaSG8mQvvO5RqGMDRJxaJ.png)

12. 点击安装目的地，点击完成，即自动分区即可；

![](https://img.imql.life/illustrations/FgPJqeVjgmUY_yRWr5wAFy8pAWvh.png)

13. 点击软件选择，附加软件处勾选标准和开发工具，完成；

![](https://img.imql.life/illustrations/FgfZ8AJmk7jUluJOV59POqBXgxQ-.png)

14. 点击网络和主机名；

![](https://img.imql.life/illustrations/FjAQGD2xwdGZDTYTAU14Vrz91sTr.png)

15. 开启以太网，不久就可看到当前自动获取到的 IP、默认路由（网关）和 DNS；

![](https://img.imql.life/illustrations/FsDMYVEl1znbg8DhIutcigANaNSK.png)

16. 点击配置，点击 IPv4 配置，选择方法为手动，点击添加，地址填上一步获取到的 IP 的以正斜杠分隔的前一部分，子网掩码填以正斜杠分隔的后一部分，网关即填以上获取到的默认路由，DNS 服务器填以上获取到的 DNS，保存；

![](https://img.imql.life/illustrations/FjnVO9xiX4yA8ttue5DwfvztHI-V.png)

17. 主机名修改为 openEuler，应用，完成；

![](https://img.imql.life/illustrations/FktFVTN7ZWywsDIfReo2VeCppmbD.png)

18. 点击根密码，为 root 用户设定密码；

![](https://img.imql.life/illustrations/Fmo62TO2hmy6OaWlThi76ShkndtE.png)

19. 开始安装，完毕后重启系统；

![](https://img.imql.life/illustrations/FoysRp1DoxXNcWBx41LhL0WRaMCa.png)
