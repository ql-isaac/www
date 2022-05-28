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

![生成ISO.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641200930911-863add42-0097-4f80-94d6-563c20bbf5c0.png#clientId=uaca46d50-f591-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u1c4f8038&margin=%5Bobject%20Object%5D&name=%E7%94%9F%E6%88%90ISO.png&originHeight=400&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=16062&status=done&style=shadow&taskId=u814dba48-7571-4d82-85bf-e16e06d543b&title=%E7%94%9F%E6%88%90ISO "生成ISO")

2. 准备一个 U 盘，将 Easy Sysprep5、Windows 10 (business edition) ISO 镜像和封装的软件放进去；
3. 安装 VMware pro 15。下载[学习版](https://www.52pojie.cn/thread-1026907-1-1.html)，安装步骤不多说了。

## 创建系统封装环境

1. 创建新的虚拟机；

![创建新的虚拟机.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641307775906-91dab40b-7b6f-49d3-8ad0-1e8ace9bd05f.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ud8c89892&name=%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E8%99%9A%E6%8B%9F%E6%9C%BA.png&originHeight=841&originWidth=1589&originalType=binary&ratio=1&rotation=0&showTitle=true&size=60189&status=done&style=shadow&taskId=ub6aec983-bca9-4fb7-9df7-4f8d91cc484&title=%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E8%99%9A%E6%8B%9F%E6%9C%BA "创建新的虚拟机")

2. 选择典型；

![典型.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641307814425-ef7073fb-a86f-42d6-9e82-2c3e7f0dab04.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u6af9694d&name=%E5%85%B8%E5%9E%8B.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=true&size=29258&status=done&style=shadow&taskId=uecac0711-7bb6-49c2-9db9-f6560d3c1cf&title=%E5%85%B8%E5%9E%8B "典型")

3. 选择安装程序光盘映像文件(iso)，选择在准备工作中制作好的 ISO；

![安装程序光盘映像文件.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641307900134-d5e0bd00-3813-44b1-89c4-43cb9349035e.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u673922bb&name=%E5%AE%89%E8%A3%85%E7%A8%8B%E5%BA%8F%E5%85%89%E7%9B%98%E6%98%A0%E5%83%8F%E6%96%87%E4%BB%B6.png&originHeight=435&originWidth=506&originalType=binary&ratio=1&rotation=0&showTitle=true&size=16654&status=done&style=shadow&taskId=ua5e8a88c-0cc6-41b0-a62f-58d6c949827&title=%E5%AE%89%E8%A3%85%E7%A8%8B%E5%BA%8F%E5%85%89%E7%9B%98%E6%98%A0%E5%83%8F%E6%96%87%E4%BB%B6 "安装程序光盘映像文件")

4. 选择客户机操作系统，按图选择即可；

![选择客户机操作系统.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641308128510-b0973abe-fdca-4c30-b2db-efffd20ba136.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u304deffd&name=%E9%80%89%E6%8B%A9%E5%AE%A2%E6%88%B7%E6%9C%BA%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F.png&originHeight=440&originWidth=513&originalType=binary&ratio=1&rotation=0&showTitle=true&size=14151&status=done&style=shadow&taskId=ud2d315f3-5fe8-48e8-8878-1fd0642de4c&title=%E9%80%89%E6%8B%A9%E5%AE%A2%E6%88%B7%E6%9C%BA%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F "选择客户机操作系统")

5. 命名虚拟机。注意默认虚拟机文件的存放位置是用户文件夹下，建议改到非 C 盘；

![命名虚拟机.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641308162440-cb13fa13-262e-4b8b-8284-8e1b9645198e.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u6e9345b3&name=%E5%91%BD%E5%90%8D%E8%99%9A%E6%8B%9F%E6%9C%BA.png&originHeight=440&originWidth=513&originalType=binary&ratio=1&rotation=0&showTitle=true&size=12723&status=done&style=shadow&taskId=ue9e8e34d-a4cc-496f-a8bf-a757dbb5231&title=%E5%91%BD%E5%90%8D%E8%99%9A%E6%8B%9F%E6%9C%BA "命名虚拟机")

6. 指定磁盘容量，考虑到会封装许多软件，容量调大些，比如 100G；

![指定磁盘容量.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641308227786-a27afdd6-b2f5-4f5a-9757-93234619ff08.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uab3b023f&name=%E6%8C%87%E5%AE%9A%E7%A3%81%E7%9B%98%E5%AE%B9%E9%87%8F.png&originHeight=440&originWidth=513&originalType=binary&ratio=1&rotation=0&showTitle=true&size=16663&status=done&style=shadow&taskId=u7696304a-391a-40bf-a60d-8ef676ca729&title=%E6%8C%87%E5%AE%9A%E7%A3%81%E7%9B%98%E5%AE%B9%E9%87%8F "指定磁盘容量")

7. 完成。

![完成.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641308299746-896cb4f4-ab89-4643-9095-8c7156417def.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uf1d56686&name=%E5%AE%8C%E6%88%90.png&originHeight=440&originWidth=513&originalType=binary&ratio=1&rotation=0&showTitle=true&size=18636&status=done&style=shadow&taskId=u86d379e5-ade2-48ed-b084-976e18f9009&title=%E5%AE%8C%E6%88%90 "完成")

## 安装原版 Windows 10 专业版

开启此虚拟机，意外发生了：

![意外发生了.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641308445594-9ef8e285-ca3e-4f51-b6d2-026a75a4ed37.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uae82f29e&name=%E6%84%8F%E5%A4%96%E5%8F%91%E7%94%9F%E4%BA%86.png&originHeight=191&originWidth=780&originalType=binary&ratio=1&rotation=0&showTitle=true&size=1519&status=done&style=shadow&taskId=u9dffca83-c7ed-4a98-823d-6b39392317b&title=%E6%84%8F%E5%A4%96%E5%8F%91%E7%94%9F%E4%BA%86 "意外发生了")

百度到了办法，先关一下机，点击编辑虚拟机设置，在高级中，固件类型选择 BIOS，确定，再开启虚拟机：

![固件类型.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641308531868-fd1fcb7b-c3cd-4a34-af1a-d2cd971238e9.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u194422c6&name=%E5%9B%BA%E4%BB%B6%E7%B1%BB%E5%9E%8B.png&originHeight=756&originWidth=745&originalType=binary&ratio=1&rotation=0&showTitle=true&size=36032&status=done&style=shadow&taskId=u40733eb3-3de4-44ce-a3d5-a5bc1027e63&title=%E5%9B%BA%E4%BB%B6%E7%B1%BB%E5%9E%8B "固件类型")

选择第二个进入 PE：

![第二个.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641308588396-6029efc0-5a60-4ac2-85db-b76d0bbb8e1c.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uebfcef77&name=%E7%AC%AC%E4%BA%8C%E4%B8%AA.png&originHeight=606&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=true&size=63785&status=done&style=shadow&taskId=ue69ca21c-279a-419a-96dc-bd241b912ba&title=%E7%AC%AC%E4%BA%8C%E4%B8%AA "第二个")

挂载 U 盘，选择准备好的 U 盘，我这里显示的是已经挂载好了的状态：

![挂载U盘.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641308695256-e34b2b34-c7d1-4809-9ff3-766a7c45cadc.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u45cbb266&name=%E6%8C%82%E8%BD%BDU%E7%9B%98.png&originHeight=364&originWidth=926&originalType=binary&ratio=1&rotation=0&showTitle=true&size=57151&status=done&style=shadow&taskId=u4ec85835-234e-436f-ae58-a54a71424f7&title=%E6%8C%82%E8%BD%BDU%E7%9B%98 "挂载U盘")

桌面上，双击 DG 硬盘分区，选择 100G 的虚拟硬盘，即我们上面分配的，点击快速分区，设置成一个分区就行：

![快速分区.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641308833235-2353ff2d-2d9a-428c-b5a3-e8ba6ee28ed3.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ub8a2d873&name=%E5%BF%AB%E9%80%9F%E5%88%86%E5%8C%BA.png&originHeight=733&originWidth=1028&originalType=binary&ratio=1&rotation=0&showTitle=true&size=81043&status=done&style=shadow&taskId=u29d31ad0-eefc-4e40-b3eb-7c66eafb8c3&title=%E5%BF%AB%E9%80%9F%E5%88%86%E5%8C%BA "快速分区")

再双击桌面中的 EIX 系统安装，左侧已经自动识别到我们 U 盘上的镜像，选择 Windows 10 专业版，右侧则是刚刚创建的那个分区，单击选择上，点击一键恢复：

![EIX系统安装.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641308922388-98752f9e-40e0-425c-8f39-234640804629.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u6e61deaa&name=EIX%E7%B3%BB%E7%BB%9F%E5%AE%89%E8%A3%85.png&originHeight=458&originWidth=652&originalType=binary&ratio=1&rotation=0&showTitle=true&size=30797&status=done&style=shadow&taskId=u64877a25-86d7-45ee-8c1d-15d35d5481e&title=EIX%E7%B3%BB%E7%BB%9F%E5%AE%89%E8%A3%85 "EIX系统安装")

这里将“恢复完成后自动运行万能驱动”勾掉，确认，等待重启：

![勾掉.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309024016-354834ef-5f0b-4d7d-b75a-7e3ef415a3ae.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uc6dc8820&name=%E5%8B%BE%E6%8E%89.png&originHeight=455&originWidth=652&originalType=binary&ratio=1&rotation=0&showTitle=true&size=46397&status=done&style=shadow&taskId=uafcaa9fb-ac8c-4227-8262-c90f1d28874&title=%E5%8B%BE%E6%8E%89 "勾掉")

## 进入审核模式

重启之后就到了这个熟悉的流程（OOBE）：

![OOBE.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309077738-9439d4f0-1a4f-494c-b4fa-0c3d729fb753.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u714ead95&name=OOBE.png&originHeight=770&originWidth=1025&originalType=binary&ratio=1&rotation=0&showTitle=true&size=30172&status=done&style=shadow&taskId=u1d045903-7ae0-4cd2-a5e0-acdf5a7028f&title=OOBE "OOBE")

不要着急点是，这里要按`Ctrl`+`Shift`+`F3`进入审核模式，刚进入是这样的：

![审核模式.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309164796-353f38be-edeb-481c-ae06-a99689143322.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u3e852279&name=%E5%AE%A1%E6%A0%B8%E6%A8%A1%E5%BC%8F.png&originHeight=773&originWidth=1030&originalType=binary&ratio=1&rotation=0&showTitle=true&size=99465&status=done&style=shadow&taskId=uee9f801e-dec8-465e-a181-fd189b96835&title=%E5%AE%A1%E6%A0%B8%E6%A8%A1%E5%BC%8F "审核模式")

注意不要点确定，点了就又退回到 OOBE 了，这里点取消：

![取消.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309290540-c73b91b5-1a58-4241-8514-aa3db378470e.png#clientId=ub3d30c00-55bb-4&crop=0.0025&crop=0&crop=1&crop=1&from=drop&height=329&id=u1590b960&name=%E5%8F%96%E6%B6%88.png&originHeight=330&originWidth=397&originalType=binary&ratio=1&rotation=0&showTitle=true&size=14758&status=done&style=shadow&taskId=uec911759-fa78-4fce-a1a9-8393791ef51&title=%E5%8F%96%E6%B6%88&width=396 "取消")

## 系统调整

1. 桌面图标设置。我习惯将“计算机”和“控制面板”显示出来；

![桌面图标设置.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309444351-59d584fe-c289-4d1d-aa8e-3abe3df307fa.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u26358616&name=%E6%A1%8C%E9%9D%A2%E5%9B%BE%E6%A0%87%E8%AE%BE%E7%BD%AE.png&originHeight=774&originWidth=1026&originalType=binary&ratio=1&rotation=0&showTitle=true&size=123907&status=done&style=shadow&taskId=u0624a493-1144-4b86-ad34-a8e27532c75&title=%E6%A1%8C%E9%9D%A2%E5%9B%BE%E6%A0%87%E8%AE%BE%E7%BD%AE "桌面图标设置")

2. 颜色偏爱设置。默认 Windows 模式改为浅色，透明效果打开，选择从我的背景自动选取一种主题色；

![颜色.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309513353-c032e9cf-c64d-4262-b266-be0303b55373.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u1f865868&name=%E9%A2%9C%E8%89%B2.png&originHeight=634&originWidth=801&originalType=binary&ratio=1&rotation=0&showTitle=true&size=27529&status=done&style=shadow&taskId=u93df35d3-b7a5-422b-838b-6f038fc38b4&title=%E9%A2%9C%E8%89%B2 "颜色")

3. 显示搜索图标。感觉搜索框太占地方了；

![显示搜索图标.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309596149-7db2ae5b-9272-42e3-bc8e-4308e7c32686.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ubd99707a&name=%E6%98%BE%E7%A4%BA%E6%90%9C%E7%B4%A2%E5%9B%BE%E6%A0%87.png&originHeight=524&originWidth=531&originalType=binary&ratio=1&rotation=0&showTitle=true&size=60101&status=done&style=shadow&taskId=ub29ec6a4-9582-47ee-bafd-bb2ca15b88b&title=%E6%98%BE%E7%A4%BA%E6%90%9C%E7%B4%A2%E5%9B%BE%E6%A0%87 "显示搜索图标")

4. 装上 Telnet 客户端。这样可以在 CMD 中使用`telnet`检测目标主机 TCP 端口是否开启；

![Telnet客户端.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309646227-014b538e-6b32-4fb4-86db-e1b02331de8d.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u598145a6&name=Telnet%E5%AE%A2%E6%88%B7%E7%AB%AF.png&originHeight=726&originWidth=1025&originalType=binary&ratio=1&rotation=0&showTitle=true&size=170632&status=done&style=shadow&taskId=u9b8217bf-3890-4064-b989-06419613a6c&title=Telnet%E5%AE%A2%E6%88%B7%E7%AB%AF "Telnet客户端")

5. 显示文件扩展名，这个必设；

![文件扩展名.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309685430-4917a1ef-c002-4e2b-889b-e6a2263c56a9.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u401181ce&name=%E6%96%87%E4%BB%B6%E6%89%A9%E5%B1%95%E5%90%8D.png&originHeight=594&originWidth=786&originalType=binary&ratio=1&rotation=0&showTitle=true&size=57934&status=done&style=shadow&taskId=udb291b1b-9170-4c78-b24f-a61ef52684b&title=%E6%96%87%E4%BB%B6%E6%89%A9%E5%B1%95%E5%90%8D "文件扩展名")

6. 系统激活，这个就不多说了；
7. 最后使用 Dism++ 对系统进行优化。

![Dism++.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309753211-2f651c42-83d3-4155-bf9f-bbab708f2f9c.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u483df1aa&name=Dism%2B%2B.png&originHeight=661&originWidth=984&originalType=binary&ratio=1&rotation=0&showTitle=true&size=40582&status=done&style=shadow&taskId=ud1578fb4-96b0-4301-998e-6d5826093ed&title=Dism%2B%2B "Dism++")

![任务栏时钟精确到秒.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309786954-4c7d3758-4fac-4981-bae0-2d73b65b598a.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u0ad366be&name=%E4%BB%BB%E5%8A%A1%E6%A0%8F%E6%97%B6%E9%92%9F%E7%B2%BE%E7%A1%AE%E5%88%B0%E7%A7%92.png&originHeight=692&originWidth=986&originalType=binary&ratio=1&rotation=0&showTitle=true&size=55640&status=done&style=shadow&taskId=uf4258dbb-0f84-4ddf-b0f7-b912176d049&title=%E4%BB%BB%E5%8A%A1%E6%A0%8F%E6%97%B6%E9%92%9F%E7%B2%BE%E7%A1%AE%E5%88%B0%E7%A7%92 "任务栏时钟精确到秒")

![桌面壁纸质量调整.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309843079-a1f14c3c-1640-4e92-a8af-a0f5ab2ae144.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u0cce12f1&name=%E6%A1%8C%E9%9D%A2%E5%A3%81%E7%BA%B8%E8%B4%A8%E9%87%8F%E8%B0%83%E6%95%B4.png&originHeight=664&originWidth=985&originalType=binary&ratio=1&rotation=0&showTitle=true&size=49368&status=done&style=shadow&taskId=u3b4fc040-bc8e-41eb-9b6a-871b269b446&title=%E6%A1%8C%E9%9D%A2%E5%A3%81%E7%BA%B8%E8%B4%A8%E9%87%8F%E8%B0%83%E6%95%B4 "桌面壁纸质量调整")

![打开资源管理器时显示此电脑.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309888463-cad16bf1-9f8f-4c91-8c59-d8ae770fe285.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u6cf22a6d&name=%E6%89%93%E5%BC%80%E8%B5%84%E6%BA%90%E7%AE%A1%E7%90%86%E5%99%A8%E6%97%B6%E6%98%BE%E7%A4%BA%E6%AD%A4%E7%94%B5%E8%84%91.png&originHeight=663&originWidth=985&originalType=binary&ratio=1&rotation=0&showTitle=true&size=58431&status=done&style=shadow&taskId=u47aa3d2c-c52b-41e5-adeb-196317a94cf&title=%E6%89%93%E5%BC%80%E8%B5%84%E6%BA%90%E7%AE%A1%E7%90%86%E5%99%A8%E6%97%B6%E6%98%BE%E7%A4%BA%E6%AD%A4%E7%94%B5%E8%84%91 "打开资源管理器时显示此电脑")

![最小化时显示完整路径.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309950200-5d54411f-a3cd-4c3d-b583-6fa5868fec0c.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ud8736dbd&name=%E6%9C%80%E5%B0%8F%E5%8C%96%E6%97%B6%E6%98%BE%E7%A4%BA%E5%AE%8C%E6%95%B4%E8%B7%AF%E5%BE%84.png&originHeight=664&originWidth=986&originalType=binary&ratio=1&rotation=0&showTitle=true&size=70363&status=done&style=shadow&taskId=u52fa7501-cf14-4fb0-8884-b994eac983e&title=%E6%9C%80%E5%B0%8F%E5%8C%96%E6%97%B6%E6%98%BE%E7%A4%BA%E5%AE%8C%E6%95%B4%E8%B7%AF%E5%BE%84 "最小化时显示完整路径")

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

![VScode.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641309981586-9944637d-0ad0-40a2-ae31-f2037634b936.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ufa0551dc&name=VScode.png&originHeight=464&originWidth=598&originalType=binary&ratio=1&rotation=0&showTitle=true&size=19821&status=done&style=shadow&taskId=u2fa7999d-bce8-4069-97f0-b844ed20b24&title=VScode "VScode")

11. 安装火绒，极速安装即可；
12. 将 Beyond Compare 放入 C 盘，为便携版，运行一下 图中 CMD 以添加右键菜单；

![添加右键菜单.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310107325-1771e8ce-2fb8-4962-b9b2-4b01805617bb.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u081b3f40&name=%E6%B7%BB%E5%8A%A0%E5%8F%B3%E9%94%AE%E8%8F%9C%E5%8D%95.png&originHeight=730&originWidth=1025&originalType=binary&ratio=1&rotation=0&showTitle=true&size=109897&status=done&style=shadow&taskId=u6839c2d6-5131-4d0b-acc9-86892bc35e2&title=%E6%B7%BB%E5%8A%A0%E5%8F%B3%E9%94%AE%E8%8F%9C%E5%8D%95 "添加右键菜单")

13. 安装 TIM，不登录；
14. 安装 WeGame，这里注意安装路径在不在 C 盘，也是不登陆；
15. 安装 Steam，下一步下一步，登录时需要验证码，填验证码时下面填一个好记的名称；

![好记的名称.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310144742-5d25d2bf-491e-4dd3-afed-4866c1fd62d3.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u0faad8c5&name=%E5%A5%BD%E8%AE%B0%E7%9A%84%E5%90%8D%E7%A7%B0.png&originHeight=421&originWidth=380&originalType=binary&ratio=1&rotation=0&showTitle=true&size=63003&status=done&style=shadow&taskId=u8ed01233-27dd-4d2a-91f3-251e862a9af&title=%E5%A5%BD%E8%AE%B0%E7%9A%84%E5%90%8D%E7%A7%B0 "好记的名称")

16. 安装战网，完成之后登录并设置为开机不自启动再退出；

## ES5 封装

运行 U 盘中的 Easy Sysprep5，点击设置，图中标记自定义即可，其他建议默认，点击封装、确定，等待上方提示完毕，重启进入 PE 执行第二阶段。

![自定义.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310258778-81af3008-81d5-4d2e-9fd1-7a663f4ba8f1.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u7ba0b566&name=%E8%87%AA%E5%AE%9A%E4%B9%89.png&originHeight=550&originWidth=759&originalType=binary&ratio=1&rotation=0&showTitle=true&size=38428&status=done&style=shadow&taskId=ud63e21f6-fefc-465b-b927-800d93009c3&title=%E8%87%AA%E5%AE%9A%E4%B9%89 "自定义")

重点来了！点击重启之后请不停按`F2`，直到进入 BIOS：

![进入BIOS.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310335905-938981f7-086b-4514-8068-fa33c25cb080.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u2a23102e&name=%E8%BF%9B%E5%85%A5BIOS.png&originHeight=480&originWidth=642&originalType=binary&ratio=1&rotation=0&showTitle=true&size=11573&status=done&style=shadow&taskId=u81273125-3d4b-41eb-929d-29205b121d6&title=%E8%BF%9B%E5%85%A5BIOS "进入BIOS")

重点没玩，左右键移动到“Boot”，然后让“CD-ROM Drive”往上移动两格，`F10`保存退出：

![调整启动顺序.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310393009-b706e4ba-d297-495e-ad24-ca10c0a8697a.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uf18d8ec9&name=%E8%B0%83%E6%95%B4%E5%90%AF%E5%8A%A8%E9%A1%BA%E5%BA%8F.png&originHeight=482&originWidth=642&originalType=binary&ratio=1&rotation=0&showTitle=true&size=12765&status=done&style=shadow&taskId=u06085c7e-f4cb-428e-a145-f0d48400d52&title=%E8%B0%83%E6%95%B4%E5%90%AF%E5%8A%A8%E9%A1%BA%E5%BA%8F "调整启动顺序")

还没完，`F10`保存退出后按两次回车，到这里也是选择第二个：

![第二个.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310457975-449dcff3-42c8-4a9d-9f1f-4d45bfa25e26.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u1b330532&name=%E7%AC%AC%E4%BA%8C%E4%B8%AA.png&originHeight=606&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=true&size=63785&status=done&style=shadow&taskId=u2cb00bc2-4020-43dc-b339-3687a1edd94&title=%E7%AC%AC%E4%BA%8C%E4%B8%AA "第二个")

再次运行 Easy Sysprep5，点击设置，优化栏里全不勾选，不需要：

![全不勾选.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310516938-4896ef2e-69ee-45ba-b197-944d7a5a6b3f.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u9cfd6073&name=%E5%85%A8%E4%B8%8D%E5%8B%BE%E9%80%89.png&originHeight=600&originWidth=784&originalType=binary&ratio=1&rotation=0&showTitle=true&size=67644&status=done&style=shadow&taskId=uf187b7d2-50df-4d23-beb9-3b469b0a1ec&title=%E5%85%A8%E4%B8%8D%E5%8B%BE%E9%80%89 "全不勾选")

部署栏里，我按下图设置的，供参考。

![部署栏.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310556798-a46d14bb-79ac-4709-b0e8-03a91df83c6f.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ud1c979bf&name=%E9%83%A8%E7%BD%B2%E6%A0%8F.png&originHeight=592&originWidth=786&originalType=binary&ratio=1&rotation=0&showTitle=true&size=52528&status=done&style=shadow&taskId=uac8d1b10-e625-4130-8a80-ea69aee7788&title=%E9%83%A8%E7%BD%B2%E6%A0%8F "部署栏")

系统栏里，我按下图设置的，供参考。

![系统栏.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310590963-f4419353-16f1-4d4c-8dd6-37d01d4efd1e.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ub7fdc510&name=%E7%B3%BB%E7%BB%9F%E6%A0%8F.png&originHeight=592&originWidth=786&originalType=binary&ratio=1&rotation=0&showTitle=true&size=47628&status=done&style=shadow&taskId=uc7b4549b-5f72-4817-b543-5774f781b5e&title=%E7%B3%BB%E7%BB%9F%E6%A0%8F "系统栏")

用户栏里，我按下图设置的，供参考。

![用户栏.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310628708-19fb7b2b-f760-4fef-b13b-a7efeab44e9c.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u1a6fa95f&name=%E7%94%A8%E6%88%B7%E6%A0%8F.png&originHeight=595&originWidth=785&originalType=binary&ratio=1&rotation=0&showTitle=true&size=29428&status=done&style=shadow&taskId=u206e44da-db7b-4d76-8f7d-4db85238340&title=%E7%94%A8%E6%88%B7%E6%A0%8F "用户栏")

其他栏中，有如图的注意，最后点击封装，确定，等待镜像备份完毕。

![其他栏.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310676806-fc52be20-185f-41ce-920e-5bf3e2e911f1.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u5da7fac7&name=%E5%85%B6%E4%BB%96%E6%A0%8F.png&originHeight=542&originWidth=759&originalType=binary&ratio=1&rotation=0&showTitle=true&size=67803&status=done&style=shadow&taskId=u0a9a7300-6d38-4ef4-a7b4-852d5cbdb5b&title=%E5%85%B6%E4%BB%96%E6%A0%8F "其他栏")

镜像备份完毕后重启，不用进行任何操作，等待部署即可：

![部署.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641310726351-a6c0879f-81b2-4aa1-8d51-92472dbaeda6.png#clientId=ub3d30c00-55bb-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u6a6fd5b8&name=%E9%83%A8%E7%BD%B2.png&originHeight=770&originWidth=1026&originalType=binary&ratio=1&rotation=0&showTitle=true&size=176181&status=done&style=shadow&taskId=ucb048f37-85dd-4876-979d-6bfd00d1a28&title=%E9%83%A8%E7%BD%B2 "部署")
