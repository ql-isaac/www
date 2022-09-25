---

title: Windows 10 封装实践

trans: The_Practice_of_Windows_10_Encapsulation

date: 2021-08-29 15:40:25

cover: https://img.imql.life/Windows_10.jpeg

tags:

- 优启通 v3.5
- Easy Sysprep v5.19.802.282 Release1
- Windows 10 专业版
- VMware® Workstation 15 Pro

categories:

- PC

---

制作一个属于自己的操作系统镜像，想想就是一件很有意义的事情！

<!-- more -->

## 准备工作

1. 使用优启通制作 PE（选择生成 ISO 的制作方式）；

![](https://img.imql.life/illustrations/FhKKIOfpurpMFN-6MmPYzA--cobF.png)

2. 准备一个 U 盘，将 Easy Sysprep5、Windows 10 (business edition) ISO 镜像和封装的软件放进去；
3. 安装 VMware pro 15。下载[学习版](https://www.52pojie.cn/thread-1026907-1-1.html)，安装步骤不多说了。

## 创建系统封装环境

1. 创建新的虚拟机；

![](https://img.imql.life/illustrations/FgdRlL67rlGMC-7iTc7AIGOPGSOl.png)

2. 选择典型；

![](https://img.imql.life/illustrations/FtuvsocoNkG7jCDF7s1htnuTHTNW.png)

3. 选择安装程序光盘映像文件(iso)，选择在准备工作中制作好的 ISO；

![](https://img.imql.life/illustrations/FrSmguYqHEOoW_8X_MZlZVPN1hzF.png)

4. 选择客户机操作系统，按图选择即可；

![](https://img.imql.life/illustrations/FuzCgK8UuaTbdRTQRPSxNne-O66h.png)

5. 命名虚拟机。注意默认虚拟机文件的存放位置是用户文件夹下，建议改到非 C 盘；

![](https://img.imql.life/illustrations/FlwvVUBML7jgEAoH6DtysFPRyDNG.png)

6. 指定磁盘容量，考虑到会封装许多软件，容量调大些，比如 100G；

![](https://img.imql.life/illustrations/Fi-3mjQO-u6xgjPyJdsdPLMwuwen.png)

7. 完成。

![](https://img.imql.life/illustrations/Fo7rCIixydravpMF6m9umEI3NpLX.png)

## 安装原版 Windows 10 专业版

开启此虚拟机，意外发生了：

![](https://img.imql.life/illustrations/Fn1Nby-8fnBLrz-kBPeSPxy-p-h_.png)

百度到了办法，先关一下机，点击编辑虚拟机设置，在高级中，固件类型选择 BIOS，确定，再开启虚拟机：

![](https://img.imql.life/illustrations/Fm4UVyolV9SOKK6-pNqVDJopxNg4.png)

选择第二个进入 PE：

![](https://img.imql.life/illustrations/Fsg9W8r8UgsM0nhtMbCIL6YjO_vS.png)

挂载 U 盘，选择准备好的 U 盘，我这里显示的是已经挂载好了的状态：

![](https://img.imql.life/illustrations/Fj2lV-baf2CB3fz6opA3PLQIHPAH.png)

桌面上，双击 DG 硬盘分区，选择 100G 的虚拟硬盘，即我们上面分配的，点击快速分区，设置成一个分区就行：

![](https://img.imql.life/illustrations/FnYfE9JXPXHxqbUq01KNQGwuRlMw.png)

再双击桌面中的 EIX 系统安装，左侧已经自动识别到我们 U 盘上的镜像，选择 Windows 10 专业版，右侧则是刚刚创建的那个分区，单击选择上，点击一键恢复：

![](https://img.imql.life/illustrations/Fon8zqIPlfBAws2qNw8JcWwxotFT.png)

这里将“恢复完成后自动运行万能驱动”勾掉，确认，等待重启：

![](https://img.imql.life/illustrations/Fv8i1mFPjxxWKCmdVKESG_1GvdUj.png)

## 进入审核模式

重启之后就到了这个熟悉的流程（OOBE）：

![](https://img.imql.life/illustrations/FvvvC1e3CQsNbVoOD9YsDNp2bKoS.png)

不要着急点是，这里要按`Ctrl`+`Shift`+`F3`进入审核模式，刚进入是这样的：

![](https://img.imql.life/illustrations/FvLtkj57QjTWauWph2IQrKizpEAy.png)

注意不要点确定，点了就又退回到 OOBE 了，这里点取消：

![](https://img.imql.life/illustrations/FrxpnRxAVLi6aYSvnw6J0Uv5mDci.png)

## 系统调整

1. 桌面图标设置。我习惯将“计算机”和“控制面板”显示出来；

![](https://img.imql.life/illustrations/FgvildZuroKF__bpcklXl7CdLt-N.png)

2. 颜色偏爱设置。默认 Windows 模式改为浅色，透明效果打开，选择从我的背景自动选取一种主题色；

![](https://img.imql.life/illustrations/Fn_iE-8WtYpMnnf2c4ce0nix_QIo.png)

3. 显示搜索图标。感觉搜索框太占地方了；

![](https://img.imql.life/illustrations/FovSMRrIFtyvacsfjtnbnt6CwqAS.png)

4. 装上 Telnet 客户端。这样可以在 CMD 中使用`telnet`检测目标主机 TCP 端口是否开启；

![](https://img.imql.life/illustrations/Ft7Dj9Pu-4_HvDZZ9sBbihtmhCAg.png)

5. 显示文件扩展名，这个必设；

![](https://img.imql.life/illustrations/FhUtqr3g-5oWXDBGGUAxMgVYHX08.png)

6. 系统激活，这个就不多说了；
7. 最后使用 Dism++ 对系统进行优化。

![](https://img.imql.life/illustrations/FtbA1XOizIA3DWJfsf9tdXpExqRR.png)

![](https://img.imql.life/illustrations/FoJWSF8xM-caFAWgwS_5xv83NgWN.png)

![](https://img.imql.life/illustrations/FrLD5Xlw8sZkeMe3ybjf47P-eZ5x.png)

![](https://img.imql.life/illustrations/FgmXA8d5CP84MwwiYkzHfUI1L0dF.png)

![](https://img.imql.life/illustrations/FqPrVcNntQetiBxNy6ROMRylzy5j.png)

## 个人必装软件和设置

1. 顺便将 Dism++ 封装进系统，这个软件还有许多地方可以探索；
2. 安装 Node.js，下一步即可；
3. 安装 Git 和 配置 Git，相关的内容在 [Git for Windows 分类](https://blog.ql-isaac.cn/categories/Git-for-Windows/) 中；
4. 安装 Notepad3，下一步即可；
5. 安装 Bandizip for Windows，默认即可；
6. Microsoft Edge 登录自己的微软账号；
7. 安装 NeatReader，登录自己的账号；
8. 安装 Typora，按推荐来即可；
9. 将 Universal Viewer Pro 放入 C 盘，为便携版；
10. 安装 Visual Studio Code，建议勾上如图的选项；

![](https://img.imql.life/illustrations/FtOXNGk5kUhDnTIaY9qr7XkKCPmu.png)

11. 安装火绒，极速安装即可；
12. 将 Beyond Compare 放入 C 盘，为便携版，运行一下 图中 CMD 以添加右键菜单；

![](https://img.imql.life/illustrations/FhztnXuXdNkI4W26ApIihIxVgsd1.png)

13. 安装 TIM，不登录；
14. 安装 WeGame，这里注意安装路径在不在 C 盘，也是不登陆；
15. 安装 Steam，下一步下一步，登录时需要验证码，填验证码时下面填一个好记的名称；

![](https://img.imql.life/illustrations/FuO1PcnNJu8fj58sn24KgX3DJWXU.png)

16. 安装战网，完成之后登录并设置为开机不自启动再退出；

## ES5 封装

运行 U 盘中的 Easy Sysprep5，点击设置，图中标记自定义即可，其他建议默认，点击封装、确定，等待上方提示完毕，重启进入 PE 执行第二阶段。

![](https://img.imql.life/illustrations/FkRiFDxtMfkFKUTREZSxVjJT_xAl.png)

重点来了！点击重启之后请不停按`F2`，直到进入 BIOS：

![](https://img.imql.life/illustrations/FivEzNk6EJYxRT1enGhxzzYOe5Bq.png)

重点没玩，左右键移动到“Boot”，然后让“CD-ROM Drive”往上移动两格，`F10`保存退出：

![](https://img.imql.life/illustrations/FlVrEC5fQ45L9dbwlFRqZrk1RM4L.png)

还没完，`F10`保存退出后按两次回车，到这里也是选择第二个：

![](https://img.imql.life/illustrations/Fsg9W8r8UgsM0nhtMbCIL6YjO_vS.png)

再次运行 Easy Sysprep5，点击设置，优化栏里全不勾选，不需要：

![](https://img.imql.life/illustrations/FlYa9iR12Cg_LzuqY_vlvIL4p5jo.png)

部署栏里，我按下图设置的，供参考。

![](https://img.imql.life/illustrations/Fuk038l5dpLDlqapEpRF7drNgywo.png)

系统栏里，我按下图设置的，供参考。

![](https://img.imql.life/illustrations/FoKnE1eenAIGXIHX1PlsXvegFkVp.png)

用户栏里，我按下图设置的，供参考。

![](https://img.imql.life/illustrations/Fk4DiPeJIRusyitrjvodxTE8iW_9.png)

其他栏中，有如图的注意，最后点击封装，确定，等待镜像备份完毕。

![](https://img.imql.life/illustrations/Fl7jULsQR7DV_OCREaYUz_9pxF-X.png)

镜像备份完毕后重启，不用进行任何操作，等待部署即可：

![](https://img.imql.life/illustrations/FmQcFl9_stksdtLqBY_FnUkKyCnM.png)
