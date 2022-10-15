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

![创建新的虚拟机.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643901328412-9c1f7f01-69ea-4b16-a113-b3361d7ea3e8.png#clientId=u175c783f-5427-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u34a5f30d&margin=%5Bobject%20Object%5D&name=%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E8%99%9A%E6%8B%9F%E6%9C%BA.png&originHeight=841&originWidth=1589&originalType=binary&ratio=1&rotation=0&showTitle=false&size=60189&status=error&style=none&taskId=ufcf2f10b-1f40-45e9-9d10-3a2e57df8e2&title=)

2. 选择典型，下一步；

![典型.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643956381555-0d73cef0-8061-4718-8278-afb7b829188d.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u7137483a&name=%E5%85%B8%E5%9E%8B.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=false&size=29258&status=error&style=shadow&taskId=u9d63442d-4c25-40b5-8900-260a4c500e1&title=)

3. 选择稍后安装操作系统，下一步；

![选择稍后安装操作系统.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643956411805-b7501bb9-4d14-47e6-8bc9-ce1569a95de2.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=ub34f6dd2&name=%E9%80%89%E6%8B%A9%E7%A8%8D%E5%90%8E%E5%AE%89%E8%A3%85%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10281&status=error&style=shadow&taskId=ud2ac32f1-bc71-4bec-a1cf-8f6af7bcd2b&title=)

4. 客户机操作系统选择 Linux，版本选择其他 Linux 5.x 或更高版本内核 64 位，下一步；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665315583058-0511f33c-adaf-44fa-919b-91193ae1218d.png#clientId=u9206f051-c3d8-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=441&id=u87159218&name=image.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=false&size=15879&status=error&style=shadow&taskId=uf24a3b95-3fe4-4023-9841-064897057a5&title=&width=456)

5. 虚拟机名称和位置自定义，下一步；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665315744231-990d144d-2aee-40d7-91b5-925b80f5b3c0.png#clientId=u9206f051-c3d8-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=441&id=u7898ef10&name=image.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13058&status=error&style=shadow&taskId=uff1d6231-c536-4194-8aee-a03d6fcfb97&title=&width=456)

6. 磁盘容量自定义。我这里就设为 60GB，下一步，完成；

![指定磁盘容量.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643956736643-c2317985-49c1-4147-9745-8909a6b75d18.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u3b40bdf0&name=%E6%8C%87%E5%AE%9A%E7%A3%81%E7%9B%98%E5%AE%B9%E9%87%8F.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11255&status=error&style=shadow&taskId=ub86684e0-edfc-48c1-b397-5ad41b5649d&title=)

7. 点击编辑此虚拟机，将内存设置为 4GB，处理器数量设为 4（一般为自己实体机处理器数量的一半）；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665316291264-c84c029e-2dcc-424d-a15d-932dd472f379.png#clientId=u9206f051-c3d8-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=750&id=u50621521&name=image.png&originHeight=938&originWidth=860&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28912&status=error&style=shadow&taskId=u639c8103-e60c-40a8-9f71-9ddcc5ffbd4&title=&width=688)

8. 点击 CD/DVD (IDE)，选择使用 ISO 映像文件，浏览，选择 openEuler 22.03 LTS 系统的 ISO 映像文件；
9. 点击网络适配器，选择桥接模式，即直接连接物理网络（实际网络），确定，开启此虚拟机，等待；
10. 回车以检查并开始安装；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665316581015-7f85f3fe-e9ed-4f85-a8e2-49bb3f9bb3d0.png#clientId=u9206f051-c3d8-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=384&id=ub15c5f8e&name=image.png&originHeight=480&originWidth=640&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5159&status=error&style=shadow&taskId=u3d1ab299-cbbf-43d1-bad4-a360640135c&title=&width=512)

11. 选择中文，继续；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665316734228-96e9de0f-d704-4e4d-8837-ec0c07993ca4.png#clientId=u9206f051-c3d8-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=480&id=uf604a080&name=image.png&originHeight=600&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=false&size=107250&status=error&style=shadow&taskId=ub9c42dc7-c9c5-4f0a-95fd-3d7149561e3&title=&width=640)

12. 点击安装目的地，点击完成，即自动分区即可；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665317387919-34ed9883-6936-4a14-b27f-d220d6abc7e4.png#clientId=u9206f051-c3d8-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=480&id=u8eb45240&name=image.png&originHeight=600&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=false&size=153374&status=error&style=shadow&taskId=u23b07147-493c-4379-92a8-903f7181994&title=&width=640)

13. 点击软件选择，附加软件处勾选标准和开发工具，完成；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665504277774-05804b17-9c55-45df-b7a1-e7a156759edf.png#clientId=uf0c645db-d936-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=480&id=u2c52bd72&name=image.png&originHeight=600&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=false&size=139365&status=done&style=shadow&taskId=u1041f882-7d10-41b6-af34-8199e20a6f0&title=&width=640)

14. 点击网络和主机名；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665493849718-0a6de3c6-feba-4691-8e1d-3fe929e19822.png#clientId=u61500bc8-25ae-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=480&id=ud47ae53e&name=image.png&originHeight=600&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=false&size=153124&status=error&style=shadow&taskId=ua00262c1-7a79-46a9-afb3-49f9f0fcbba&title=&width=640)

15. 开启以太网，不久就可看到当前自动获取到的 IP、默认路由（网关）和 DNS；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665494426316-83469258-70af-4dc3-8d64-5d3a1e62a523.png#clientId=u61500bc8-25ae-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=480&id=u407c9340&name=image.png&originHeight=600&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=false&size=100376&status=error&style=shadow&taskId=u3c72def5-fff7-4db8-87a5-f07746935d0&title=&width=640)

16. 点击配置，点击 IPv4 配置，选择方法为手动，点击添加，地址填上一步获取到的 IP 的以正斜杠分隔的前一部分，子网掩码填以正斜杠分隔的后一部分，网关即填以上获取到的默认路由，DNS 服务器填以上获取到的 DNS，保存；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665495088457-a3005155-7b80-4d98-9d06-ce015da9655b.png#clientId=u61500bc8-25ae-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=480&id=u0e154921&name=image.png&originHeight=600&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=false&size=90505&status=error&style=shadow&taskId=u4c51d74f-38f3-4c49-b97a-213057015b0&title=&width=640)

17. 主机名修改为 openEuler，应用，完成；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665504527949-207ae5d1-b0b9-499d-90a3-b770a9819f0e.png#clientId=uf0c645db-d936-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=480&id=u3114891c&name=image.png&originHeight=600&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=false&size=99972&status=done&style=shadow&taskId=ue57a13d3-5634-471f-9d70-918b63e0d47&title=&width=640)

18. 点击根密码，为 root 用户设定密码；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665317637346-bd54b1fa-0d15-46ef-bd87-fbd9e79b7787.png#clientId=u9206f051-c3d8-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=480&id=uf337458c&name=image.png&originHeight=600&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=false&size=153176&status=error&style=shadow&taskId=u8344b46d-f19a-44ea-8665-4f02856f590&title=&width=640)

19. 开始安装，完毕后重启系统；

![image.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1665317898154-566fbf7f-6f1f-44ea-822c-081ed5a9f067.png#clientId=u9206f051-c3d8-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=480&id=u8b909cd1&name=image.png&originHeight=600&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=false&size=91698&status=error&style=shadow&taskId=u51a387af-3fc9-4cbb-8320-81dc75ad303&title=&width=640)
