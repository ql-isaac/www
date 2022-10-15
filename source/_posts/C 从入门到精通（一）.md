---

title: C 从入门到精通（一）

trans: C_Learning_1

date: 2020-02-13 19:56:24

cover: https://img.imql.life/C.jpg

tags:

- Ubuntu 18.04 LTS
- VMware® Workstation 15 Pro

categories:

- C 从入门到精通

---

任何比 C 语言更低级的语言，都不足以完整地抽象一个计算机系统，任何比 C 语言高级的语言，都可以用 C 语言实现。C 语言不像是被发明的，它更像是被发现的，它无可替代、精妙绝伦。

<!-- more -->

## C 语言的简单历史

C 语言是从 B 语言发展而来，B 语言是从 BCPL 发展而来，BCPL 是从 FORTRAN 发展而来。C 语言于 1972 年 11 月问世，1973 年 3 月，第三版的 Unix 上出现了 C 语言的编译器，1973 年 11 月，第四版的 Unix 发布了，这个版本是完全用 C 语言重新写的，1978 年美国电话电报公司（AT&T）贝尔实验室正式发布 C 语言，1983 年美国国家标准局（American National Standards Institute，简称 ANSI）开始制定 C 语言标准，于 1989 年 12 月完成，并在 1990 年春天发布，称之为 ANSI C，有时也被称为 C89 或 C90。

## 搭建学习环境

### 安装 VMware

下载[学习版](https://www.52pojie.cn/thread-1026907-1-1.html)，安装步骤不多说了，只是有一点建议，也是我装软件的原则：能不装 C 盘就别装 C 盘。

### 下载系统镜像

### 安装系统镜像

1. VMware pro 15 安装完成后，启动，点击创建新的虚拟机；

![创建新的虚拟机.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643956356143-15d3b7c0-0951-4816-b49f-490d3f7809ab.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=ua3767e79&name=%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E8%99%9A%E6%8B%9F%E6%9C%BA.png&originHeight=841&originWidth=1589&originalType=binary&ratio=1&rotation=0&showTitle=false&size=60189&status=error&style=shadow&taskId=ufa12c30c-9f8f-4a08-be07-d53cb40786b&title=)

2. 选择典型，下一步；

![典型.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643956381555-0d73cef0-8061-4718-8278-afb7b829188d.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u7137483a&name=%E5%85%B8%E5%9E%8B.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=false&size=29258&status=error&style=shadow&taskId=u9d63442d-4c25-40b5-8900-260a4c500e1&title=)

3. 选择稍后安装操作系统，下一步；

![选择稍后安装操作系统.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643956411805-b7501bb9-4d14-47e6-8bc9-ce1569a95de2.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=ub34f6dd2&name=%E9%80%89%E6%8B%A9%E7%A8%8D%E5%90%8E%E5%AE%89%E8%A3%85%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10281&status=error&style=shadow&taskId=ud2ac32f1-bc71-4bec-a1cf-8f6af7bcd2b&title=)

4. 客户机操作系统选择 Linux，版本选择 Ubuntu 64 位，下一步；

![选择客户机操作系统.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643956433849-d056bd06-d567-48ee-892c-23a0c3e1429b.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u9a497836&name=%E9%80%89%E6%8B%A9%E5%AE%A2%E6%88%B7%E6%9C%BA%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=false&size=8071&status=error&style=shadow&taskId=u5ef93558-8a70-4b56-b64c-413e4ec23c8&title=)

5. 虚拟机名称和位置自定义，下一步；

![虚拟机名称和位置.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643956600639-2f6c25e2-492c-4315-beeb-a1a56fbc8fe6.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=uf1bfd887&name=%E8%99%9A%E6%8B%9F%E6%9C%BA%E5%90%8D%E7%A7%B0%E5%92%8C%E4%BD%8D%E7%BD%AE.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=false&size=7777&status=error&style=shadow&taskId=u286d7e2e-b420-46a2-b887-c5b7f3ed273&title=)

6. 磁盘容量自定义。我这里就设为 60GB，下一步，完成；

![指定磁盘容量.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643956736643-c2317985-49c1-4147-9745-8909a6b75d18.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u3b40bdf0&name=%E6%8C%87%E5%AE%9A%E7%A3%81%E7%9B%98%E5%AE%B9%E9%87%8F.png&originHeight=551&originWidth=570&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11255&status=error&style=shadow&taskId=ub86684e0-edfc-48c1-b397-5ad41b5649d&title=)

7. 点击编辑此虚拟机，将处理器数量设为 4（一般为自己实体机处理器数量的一半）；

![处理器数量.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643957622343-73b6dd3c-d10b-4e60-b743-68ef1b9950a0.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u0584d56b&name=%E5%A4%84%E7%90%86%E5%99%A8%E6%95%B0%E9%87%8F.png&originHeight=939&originWidth=860&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24588&status=error&style=shadow&taskId=u767e188e-93a7-44d1-b691-35ce2d9eff6&title=)

8. 点击 CD/DVD (SATA)，选择使用 ISO 映像文件，浏览，选择 Ubuntu 18.04 LTS 系统的 ISO 映像文件，确定，点击开启此虚拟机，等待；

![选择系统镜像.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643957660423-fb1376de-cc9f-44cf-80d0-9fb76de48fed.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u96610e9f&name=%E9%80%89%E6%8B%A9%E7%B3%BB%E7%BB%9F%E9%95%9C%E5%83%8F.png&originHeight=939&originWidth=860&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20794&status=error&style=shadow&taskId=u994e9658-46f6-46e6-9214-289ff0afff9&title=)

9. 选择中文(简体)，再选择安装 Ubuntu；

![中文简体.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643958452623-bb42c4f3-f7ae-4e25-8dc2-4ff2b151cb3e.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u027eddee&name=%E4%B8%AD%E6%96%87%E7%AE%80%E4%BD%93.png&originHeight=617&originWidth=820&originalType=binary&ratio=1&rotation=0&showTitle=false&size=61576&status=error&style=shadow&taskId=u731dc6e3-c42d-472e-8497-e2061444665&title=)

10. 继续；

![继续.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643958493816-e08026ab-0338-4cee-9d9a-84e93b462110.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u25a1e5fb&name=%E7%BB%A7%E7%BB%AD.png&originHeight=613&originWidth=817&originalType=binary&ratio=1&rotation=0&showTitle=false&size=46386&status=error&style=shadow&taskId=ua59b247e-b85d-4d50-9d24-bdc930d1e1c&title=)

11. 勾选最后一个，继续；

![勾选.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643958957763-dd7624dd-ee2a-4fad-80db-195d228eea69.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u019ab080&name=%E5%8B%BE%E9%80%89.png&originHeight=621&originWidth=823&originalType=binary&ratio=1&rotation=0&showTitle=false&size=57577&status=error&style=shadow&taskId=u68b1a2aa-6e15-4812-9db5-3cd3c62f5ca&title=)

12. 现在安装；

![现在安装.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643959418680-3992ac82-6b9b-4da9-9e0d-06254d64f952.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u4901eff4&name=%E7%8E%B0%E5%9C%A8%E5%AE%89%E8%A3%85.png&originHeight=635&originWidth=823&originalType=binary&ratio=1&rotation=0&showTitle=false&size=63079&status=error&style=shadow&taskId=ucb65a80c-0e0f-4215-9f5e-9b3e84e4299&title=)

13. 继续；

![再次确认.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643959737690-08d17aab-8022-4b1b-a018-a921919f9307.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u80362f10&name=%E5%86%8D%E6%AC%A1%E7%A1%AE%E8%AE%A4.png&originHeight=616&originWidth=818&originalType=binary&ratio=1&rotation=0&showTitle=false&size=62682&status=error&style=shadow&taskId=u1fe2ed93-ed2d-46c9-bae0-4414f39d759&title=)

14. 在地图上点击，选择 shanghai，继续；

![shanghai.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643959781159-33673d13-5633-4370-a8b7-64ea9a742f47.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=ua12580a2&name=shanghai.png&originHeight=616&originWidth=817&originalType=binary&ratio=1&rotation=0&showTitle=false&size=110696&status=error&style=shadow&taskId=u76409333-533e-456d-98b5-49775747238&title=)

15. 自定义信息，继续；

![您是谁.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961038509-a0f8c0a4-a397-485a-8578-96de84f55690.png#clientId=u9e62351f-20ea-4&crop=0.0107&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&height=621&id=ucf0de6d9&name=%E6%82%A8%E6%98%AF%E8%B0%81.png&originHeight=628&originWidth=829&originalType=binary&ratio=1&rotation=0&showTitle=false&size=44087&status=error&style=shadow&taskId=uaecbd7b1-9067-4b01-a944-de6d789427b&title=&width=820)

16. 等待；

![等待.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961084777-b23c620c-69c1-41f3-9397-e95d46ea0b18.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u8b80b1f5&name=%E7%AD%89%E5%BE%85.png&originHeight=622&originWidth=823&originalType=binary&ratio=1&rotation=0&showTitle=false&size=159278&status=error&style=shadow&taskId=u6dd4c45a-ca0a-4404-853c-d525ce18750&title=)

17. 现在重启；

![现在重启.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961125647-ea1d3e47-073a-4282-b28f-6270248f2c1c.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=ue56bce6e&name=%E7%8E%B0%E5%9C%A8%E9%87%8D%E5%90%AF.png&originHeight=638&originWidth=827&originalType=binary&ratio=1&rotation=0&showTitle=false&size=92322&status=error&style=shadow&taskId=u781a7cde-48dd-48dd-9771-72136556a43&title=)

18. 登录刚创建的用户。

![登录.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961155335-c7ea6502-dac8-480a-9e7b-6b20afa3f765.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u2439867f&name=%E7%99%BB%E5%BD%95.png&originHeight=647&originWidth=875&originalType=binary&ratio=1&rotation=0&showTitle=false&size=184331&status=error&style=shadow&taskId=u856f0bf1-95be-4edd-bfab-f2a51a49315&title=)

### 安装 VMware Tools

可以安装上 VMware Tools 让我们拥有最佳的 Ubuntu 18.04 LTS 操作体验，如在实体机上一般。首先点击左上方的虚拟机，再点击安装 VMware Tools，这时会在桌面出现一个 DVD，接下来具体安装过程如下：

![安装VMware_Tools.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1643961297695-2aec177a-0c54-4fa3-adcd-831bd77140da.gif#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u12fb2c8d&name=%E5%AE%89%E8%A3%85VMware_Tools.gif&originHeight=597&originWidth=802&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5697241&status=error&style=shadow&taskId=u242d3de2-1890-4b82-ae60-fd3a7d3b299&title=)

### 设置阿里镜像

1. 打开软件更新器；

![软件更新器.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961330765-81f0045e-2e3b-4cc1-8a35-f0128d5bb97a.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u6ccac1f3&name=%E8%BD%AF%E4%BB%B6%E6%9B%B4%E6%96%B0%E5%99%A8.png&originHeight=886&originWidth=1919&originalType=binary&ratio=1&rotation=0&showTitle=false&size=346279&status=error&style=shadow&taskId=u768fb06b-856e-432d-ab74-efd19d7545d&title=)

2. 一般会有更新提示，先不更新，点击设置；

![设置.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961379812-c073c13b-8d56-45ba-99bf-83944086d1fa.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u62d633c9&name=%E8%AE%BE%E7%BD%AE.png&originHeight=883&originWidth=1913&originalType=binary&ratio=1&rotation=0&showTitle=false&size=241570&status=error&style=shadow&taskId=uc7f14975-52bd-4769-b194-3665bb85e0a&title=)

3. 点击 Ubuntu 软件，设置下载源；

![Ubuntu软件.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961473756-d6d41100-feac-43da-9bb2-6963b85bfe99.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u35bbdf01&name=Ubuntu%E8%BD%AF%E4%BB%B6.png&originHeight=879&originWidth=1914&originalType=binary&ratio=1&rotation=0&showTitle=false&size=282900&status=error&style=shadow&taskId=ueb91d9cd-4ef7-4f15-b458-4ed07b7bcfd&title=)

4. 点击其他站点，选择阿里云镜像站点，需要输入用户密码认证；

![aliyun.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961509464-91867720-7db3-4b3a-92ee-b83f72eea6c4.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=uaa5e860f&name=aliyun.png&originHeight=883&originWidth=1912&originalType=binary&ratio=1&rotation=0&showTitle=false&size=262126&status=error&style=shadow&taskId=ue3f85507-7faa-419d-8d55-409e86c1e3a&title=)

5. 重新载入可用软件包列表；

![重新载入.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961544900-d0cceb89-9a97-4f2a-be7c-4bddc4994b65.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u793ea9cc&name=%E9%87%8D%E6%96%B0%E8%BD%BD%E5%85%A5.png&originHeight=882&originWidth=1916&originalType=binary&ratio=1&rotation=0&showTitle=false&size=265126&status=error&style=shadow&taskId=u9d9343b9-4e4e-4184-8172-2fa43cf058e&title=)

6. 现在和以后就可以高速安装更新或软件包了，点击立即安装；

![更新.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961571319-5257d4d6-85c8-4a50-b379-afbc888e30ee.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u29f79f06&name=%E6%9B%B4%E6%96%B0.png&originHeight=497&originWidth=735&originalType=binary&ratio=1&rotation=0&showTitle=false&size=85616&status=error&style=shadow&taskId=u01045224-9ede-4a65-a756-6b686fc75c2&title=)

### 美化自己的 Ubuntu 18.04 LTS

1. 右键点击桌面，在终端打开，输入以下命令回车，输入用户密码安装 gnome-tweak-tool 软件包；

```bash
sudo apt install gnome-tweak-tool
```

2. 火狐浏览器访问 [GNOME Shell Extensions](https://extensions.gnome.org)，点击安装该浏览器扩展；

![安装浏览器扩展.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961616683-13e11b89-5cb3-4664-8905-53355cbbae52.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u38141e8b&name=%E5%AE%89%E8%A3%85%E6%B5%8F%E8%A7%88%E5%99%A8%E6%89%A9%E5%B1%95.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=160023&status=error&style=shadow&taskId=ueb0250bc-fd16-4a2f-a3e9-6268291c3df&title=)

3. 刷新一下浏览器，这时会有错误信息，右键点击桌面，在终端打开，输入以下命令回车，输入用户密码安装 chrome-gnome-shell 软件包，再刷新一下浏览器，错误消失了；

```bash
sudo apt install chrome-gnome-shell
```

![错误.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961689002-7dea3add-50b0-4ff4-a942-47a6a92a5b8a.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u6d005753&name=%E9%94%99%E8%AF%AF.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=158197&status=error&style=shadow&taskId=ue33d860f-0503-4b9c-b891-839fa1f8aa6&title=)

4. 分别点击两个 GNOME Shell 扩展：User Themes 和 Dash to Dock，将它们都开启（即安装）；

![两个扩展.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961801689-47336a23-0d56-47da-959b-15f039b9e14f.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u2eaa4253&name=%E4%B8%A4%E4%B8%AA%E6%89%A9%E5%B1%95.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=164885&status=error&style=shadow&taskId=ub790476f-404a-422e-b736-de43b5aff68&title=)

5. 在安装完 Dash to Dock 时，你会发现侧边栏消失了，相信这是大多数人想要的效果；

![侧边栏消失了.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961827400-0098521f-0729-4612-8de4-477832a443d5.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u1311bc15&name=%E4%BE%A7%E8%BE%B9%E6%A0%8F%E6%B6%88%E5%A4%B1%E4%BA%86.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=125624&status=error&style=shadow&taskId=uf4d7586b-4725-4893-8011-d2937373959&title=)

6. 打开优化；

![优化.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961853939-98794544-9e6e-40f5-84d7-9f2d843efcfa.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u3d1186b9&name=%E4%BC%98%E5%8C%96.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=558192&status=error&style=shadow&taskId=u83dfaba7-80cf-4bc0-be28-4fcb1fa9f47&title=)

7. 打开 Dash to Dock 的设置；

![DashtoDock设置.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961890857-46d68b05-56c0-4b2b-a1c9-ce39c7339243.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=uecdd11bd&name=DashtoDock%E8%AE%BE%E7%BD%AE.png&originHeight=635&originWidth=883&originalType=binary&ratio=1&rotation=0&showTitle=false&size=59093&status=error&style=shadow&taskId=u0204fca5-0a55-4a12-a846-a7850d90a21&title=)

8. 打开智能隐藏的设置；

![智能隐藏的设置.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643961921900-dfe0af3a-24e3-4257-a486-0590cb40664b.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u430ca138&name=%E6%99%BA%E8%83%BD%E9%9A%90%E8%97%8F%E7%9A%84%E8%AE%BE%E7%BD%AE.png&originHeight=699&originWidth=606&originalType=binary&ratio=1&rotation=0&showTitle=false&size=56583&status=error&style=shadow&taskId=u3a0a7d15-cc9f-4369-a7b2-bb8dfb79f4e&title=)

9. 勾选在全屏状态下启用，不勾选推压以显示......，调整显示超时时间为 0.2 秒，关闭窗口，此时，再打开火狐浏览器，当把鼠标移动到左侧，侧边栏自动显示，移走鼠标，侧边栏自动隐藏，相信这同样是大多数人想要的效果；

![设置和调整.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643962423678-8c60001f-7b75-4936-aa2a-d169283bd156.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=paste&height=481&id=u68e99eb5&name=%E8%AE%BE%E7%BD%AE%E5%92%8C%E8%B0%83%E6%95%B4.png&originHeight=601&originWidth=435&originalType=binary&ratio=1&rotation=0&showTitle=false&size=57335&status=error&style=shadow&taskId=u8907399c-bd73-4bec-b2d8-d6584610eef&title=&width=348)

![智能隐藏.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1643962821708-9db433ae-fbc9-4272-b3d0-fd46efe4415a.gif#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=ud0e288e8&name=%E6%99%BA%E8%83%BD%E9%9A%90%E8%97%8F.gif&originHeight=873&originWidth=801&originalType=binary&ratio=1&rotation=0&showTitle=false&size=330566&status=error&style=shadow&taskId=u7f257c28-89df-4237-8226-ef8f0e48439&title=)

10. 打开火狐浏览器，进入[该网址](https://www.gnome-look.org/p/1275087/)下载 McMojave 主题，等待，确定；

![下载主题.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643962848908-6d404dc0-b3fd-45a0-9d14-8456a82d3370.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=ucf19c5d7&name=%E4%B8%8B%E8%BD%BD%E4%B8%BB%E9%A2%98.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=384432&status=error&style=shadow&taskId=uc79d9c16-7182-49f8-b98f-81a15b50ea7&title=)

11. 提取到下载中，点击显示文件；

![提取.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643962873144-1c825bbb-0c09-4862-a6b7-92dce17839c2.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=uebd26bdb&name=%E6%8F%90%E5%8F%96.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=208363&status=error&style=shadow&taskId=u04f2842b-db82-407a-a1f1-9769fc35457&title=)

12. 右键，在终端打开；

![右键.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643962901077-9d211624-b4cb-4b83-8439-3cfd5a00df43.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u7cf55d43&name=%E5%8F%B3%E9%94%AE.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=251320&status=error&style=shadow&taskId=u7dfa903a-fbff-4d3b-b93c-9a6c0db7084&title=)

13. 输入以下命令回车，输入用户密码，移动 Mojave-light 目录；

```bash
sudo mv Mojave-light/ /usr/share/themes/
```

14. 打开优化，选择 Mojave-light 主题，就能看到效果了；

![更换主题.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1643962941600-ae52c85b-dccb-48bd-864f-cb0b04f321fc.gif#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u7291d034&name=%E6%9B%B4%E6%8D%A2%E4%B8%BB%E9%A2%98.gif&originHeight=880&originWidth=1826&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3446758&status=error&style=shadow&taskId=ub2c7f83c-a5b3-442d-b842-102bd3097ac&title=)

15. [进入该网址](https://www.gnome-look.org/p/1305429/)，下载 McMojave-circle 图标，等待，确定；

![下载图标.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643962978436-4eb611fc-612c-4525-b035-9d1606e35845.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u69a28e4b&name=%E4%B8%8B%E8%BD%BD%E5%9B%BE%E6%A0%87.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=299869&status=error&style=shadow&taskId=ud64c2509-8b3c-4c8a-af4d-841b5545539&title=)

16. 同上，提取到下载中，点击显示文件，右键，在终端打开，输入以下命令回车，输入用户密码，移动 McMojave-circle 目录；

```bash
sudo mv McMojave-circle/ /usr/share/icons/
```

17. 打开优化，选择 McMojave-circle 图标，就能看到效果了；

![更换图标.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1643963029037-6d70a0c9-f49d-47ff-a84f-d8b6f72771a0.gif#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u5955c772&name=%E6%9B%B4%E6%8D%A2%E5%9B%BE%E6%A0%87.gif&originHeight=874&originWidth=1822&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2960358&status=error&style=shadow&taskId=ua29f7b98-76e2-4397-a6a7-448820a23d1&title=)

18. 有一个地方忘记了，打开优化，选择 shell 为 Mojave-light；

![更换shell.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1643963066191-44adc533-fb44-4254-9aff-0d1bdec8bb55.gif#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=ud08c0062&name=%E6%9B%B4%E6%8D%A2shell.gif&originHeight=877&originWidth=1820&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1560126&status=error&style=shadow&taskId=ua2bdca59-0dd9-4ba9-8164-c5a1484282d&title=)

19. 可以在 Dash to Dock 设置中设置侧边栏的位置在底部；

![设置在底部.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643963108213-adc1f72c-2adb-4679-be62-47e0f694050e.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u9cb8615a&name=%E8%AE%BE%E7%BD%AE%E5%9C%A8%E5%BA%95%E9%83%A8.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=262000&status=error&style=shadow&taskId=uaae73c44-e327-4215-8242-5d0b659097d&title=)

20. 最后，在优化->窗口中，设置标题栏按钮在左边，右键桌面更换个壁纸，至此，美化算是告一段落了。

### 安装 build-essential 软件包和 Vim 文本编辑器

右键点击桌面，在终端打开，输入以下命令回车，输入用户密码安装 build-essential 软件包。

```bash
sudo apt-get install build-essential
```

再输入以下命令回车，输入用户密码安装 Vim 文本编辑器。

```bash
sudo apt-get install vim
```

## 注释

如何注释应该是我们学习任何一门编程语言最先需要知道的，C 语言中有两种注释方式：

- 以`/*`开始`*/`结束的块注释（block comment）；
- 以`//`开始换行符结束的单行注释（line comment）；

## C 语言学习起步

右键点击桌面，新建一个学习文件夹 C Learning，点开，再新建文件夹（一），再点开，再新建文件夹 20200404 ，再点开，右键，在终端打开。

### 新建 hello_world.c 源文件、用 Vim 编辑并保存

输入以下命令新建 hello_world.c 源文件并用 Vim 打开：

```bash
vim hello_world.c
```

![hello_world.c.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1664097703086-9c449d23-4269-405b-8f9f-93e6e2a37da9.png#clientId=uecacb1e1-2312-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u9ebe5eff&name=hello_world.c.png&originHeight=496&originWidth=735&originalType=binary&ratio=1&rotation=0&showTitle=false&size=31995&status=error&style=shadow&taskId=u401d2a7f-93ba-4e60-9496-4bacaee88e1&title=)

按下 i 键进入插入模式，国际惯例，编写第一个程序：打印”Hello,World!“：

```c
#include <stdio.h>
int main(){
    printf("Hello,World!\n"); //print是打印的意思，f是format的简写，printf()函数的功能就是格式化输出
    return 0;
}
```

按下 ESC 键进入一般模式，再按”SHIFT+;“（即输入英文的分号）进入命令模式，输入 wq 命令（write and quit），这样源文件就保存了。

![保存.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1664097751833-7d5b26ec-805b-4be2-badd-82801bd4c84a.gif#clientId=uecacb1e1-2312-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u52eda942&name=%E4%BF%9D%E5%AD%98.gif&originHeight=491&originWidth=733&originalType=binary&ratio=1&rotation=0&showTitle=false&size=81093&status=error&style=shadow&taskId=u2e5a1f4e-9535-4a8f-9e60-1ea785c36a3&title=)

### 编译

之后就是编译，输入以下命令回车执行（小技巧：打 hello_world.c 时，可以只打 h 再按 TAB 键，系统能自动匹配）：

```bash
gcc hello_world.c
```

输入以上命令后没有任何提示，别慌，这是正常的，在 Linux 中，没有消息就是好消息。可以输入以下命令(`ls -alF *`的别名）列出当前目录下有哪些文件和目录，./指的是当前目录，../指的是上一级目录，hello_world.c 是刚刚保存的 C 源文件，那这个“a.out\*”是什么呢？没错，就是刚刚编译出来的可执行文件（ 星号表示该文件为可执行文件）。

```bash
ll
```

![a.out.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1664097789947-743698f0-3c9d-4470-9a27-26727791b500.png#clientId=uecacb1e1-2312-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=ue479e4ba&name=a.out.png&originHeight=491&originWidth=733&originalType=binary&ratio=1&rotation=0&showTitle=false&size=49594&status=error&style=shadow&taskId=uda5e9209-bc14-45d1-8550-4cd3b0b1f36&title=)

### 运行

有了可执行文件，就可以运行了，输入以下命令执行就能打印出“Hello,World!”了。

```bash
./a.out
```

![打印结果.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1664097837184-7a35f44c-cbb4-4c6a-98ec-a025964eaed8.png#clientId=uecacb1e1-2312-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u47505f33&name=%E6%89%93%E5%8D%B0%E7%BB%93%E6%9E%9C.png&originHeight=490&originWidth=731&originalType=binary&ratio=1&rotation=0&showTitle=false&size=56132&status=error&style=shadow&taskId=uca7160d9-7d3c-414c-954c-479b88afee0&title=)

### 小结

以上就是 C 学习的起步内容，下面就开始正式的学习，会总是需要用到上面提到的新建并编辑保存、编译和运行的相关命令，还有一个小技巧，可以使用键盘的方向键上和下在历史命令中切换。

## 做点计算

范例：做点计算（新建 compute.c）

```c
#include <stdio.h>

int main(){
    printf("12+34=%d\n",12+34); //%d为占位符，表示数据打印出来的格式应该是十进制整数的格式
    return 0;
}
```

打印结果：

```
12+34=46
```

除了做加法，当然还能做其他运算：

| 运算   | 运算符 |
| ------ | ------ |
| 加     | +      |
| 减     | -      |
| 乘     | \*     |
| 除     | /      |
| 取余数 | %      |
| 括号   | ()     |

## 变量

### 变量类型

C 语言是一种强类型的语言，所有的变量都必须有类型。

### 变量定义

变量定义的一般形式：

```
<类型名称> <变量名称>;
```

范例：定义变量 price，存放价格的 int 型数据，定义变量 payment，存放支付金额的 int 型数据

```c
int price;
int payment;
```

或

```c
int price,payment; //可以在一行中定义多个同类型的变量，有逗号分隔
```

### 标识符

标识符只能由字母、数字和下划线组成，数字不能出现在第一个字符的位置，标识符分为关键字，预定义标识符和用户自定义标识符，变量名称就属于用户自定义标识符。

### 赋值运算符

赋值也是一种运算，运算符为`=`，表示将右边的值复制一份赋给左边的变量，那么，这和数学中的等于号是一样的吗？当然不是，数学中的等于号表示的是相等的关系，C 语言也有表示相等关系的运算符，即`==`。

范例：使用赋值运算符初始化变量

```
int price=56;
int payment=100;
```

或

```
int price;
int payment;
price=56;
payment=100;
```

或

```
int price=56,payment=100;
```

### 用 scanf()函数初始化变量

范例：定义 price 和 payment 并用 scanf() 函数初始化它们

```c
int price,payment;
printf("请输入该商品价格（元）：");
scanf("%d",&price); //scan是扫描的意思，f同样是format的简写，scanf()函数的功能就是格式化扫描,扫描什么？扫描字符呗，以回车为结束符（不计入输入中）将输入的字符以十进制整数的格式解析，&price的意思就是将解析出来的值复制一份赋给price
printf("请输入支付的金额（元）：");
scanf("%d",&payment); //同上
```

### 变量的使用

范例：找零（新建 change.c)

```c
#include <stdio.h>

int main(){
    int price;
    int payment;
    printf("请输入该商品价格（元）：");
    scanf("%d",&price); //键盘输入的方式初始化price
    printf("请输入支付的金额（元）：");
    scanf("%d",&payment); //键盘输入的方式初始化payment
    int change=payment-price;
    printf("找零（元）：%d\n",change);
    return 0;
}
```

运行结果：

![change.c.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1664097926061-e696ef2d-3720-4429-95a1-f641b36b2554.gif#clientId=uecacb1e1-2312-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=ued16b757&name=change.c.gif&originHeight=491&originWidth=733&originalType=binary&ratio=1&rotation=0&showTitle=false&size=50710&status=error&style=shadow&taskId=u3ff70c84-8884-434e-9df5-dd780734fb3&title=)

### 没有初始化变量的后果

范例：没有初始化 payment（修改 change.c)

```c
#include <stdio.h>

int main(){
    int price;
    int payment;
    printf("请输入该商品价格（元）：");
    scanf("%d",&price); //键盘输入的方式初始化price
    int change=payment-price;
    printf("找零（元）：%d\n",change);
    return 0;
}
```

运行结果：

![没有初始化变量.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1664097957545-26483fff-6468-4f54-bd32-4e9aba7d2254.gif#clientId=uecacb1e1-2312-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u427abe5a&name=%E6%B2%A1%E6%9C%89%E5%88%9D%E5%A7%8B%E5%8C%96%E5%8F%98%E9%87%8F.gif&originHeight=489&originWidth=732&originalType=binary&ratio=1&rotation=0&showTitle=false&size=47931&status=error&style=shadow&taskId=ufae13966-3c0c-4420-ba82-7a69d6b5318&title=)

什么！找零 2 亿多？？！！原来，变量在没有初始化，也就是刚一定义时，其实就是有值的，可是这个值只有计算机知道，在发生意想不到的问题之前，我们应该时刻注意变量在定义后一定要初始化。

## 常量

### 定义常量

变量定义的一般形式：

```c
const <类型名称> <常量名称>; //const是一个修饰符，是constant（常数）的简写，规定常量名称中的字母都为大写，这是命名规范
```

### 常量和变量的相同点和不同点

相同点：常量和变量都需要初始化。

不同点：常量在初始化后不能再被修改而变量可以。

### 常量的使用

在找零程序中，该商品，比如说一本书，它的价格就是 56 元，没必要总是输入 56，于是我们可以这么写：

范例：使用常量（修改 change.c)

```c
#include <stdio.h>

int main(){
    const int PRICE=56;
    int payment;
    printf("请输入支付的金额（元）：");
    scanf("%d",&payment); //键盘输入的方式初始化payment
    int change=payment-PRICE;
    printf("找零（元）：%d\n",change);
    return 0;
}
```

如果我们尝试去修改 PRICE 会如何？来试一下：

范例：尝试修改 PRICE（修改 change.c)

```c
#include <stdio.h>

int main(){
    const int PRICE=56;
    int payment;
    printf("请输入该商品价格（元）：");
    scanf("%d",&PRICE); //尝试修改PRICE
    printf("请输入支付的金额（元）：");
    scanf("%d",&payment); //键盘输入的方式初始化payment
    int change=payment-PRICE;
    printf("找零（元）：%d\n",change);
    return 0;
}
```

运行结果：

![尝试修改PRICE.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1664098001944-2425bec6-79d0-4ffe-a68a-19eac3b32f26.gif#clientId=uecacb1e1-2312-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u212ccfda&name=%E5%B0%9D%E8%AF%95%E4%BF%AE%E6%94%B9PRICE.gif&originHeight=494&originWidth=734&originalType=binary&ratio=1&rotation=0&showTitle=false&size=62900&status=error&style=shadow&taskId=udbd25290-c18f-4a01-9d70-52b781dc179&title=)

## 浮点型

美国人习惯用几英尺几英寸的方式描述自己的身高，如果遇到一个美国人告诉你他的身高为 5 英尺 7 英寸，他的身高应该是一米几呢？由于 1 英尺 = 12 英寸 = 0.3048 米，所以 5 英尺 7 英寸应该为 (5+7/12)\*0.3048 米，即 1.7018 米。来写个程序：

范例：长度换算（新建 length_conversion.c)

```c
#include <stdio.h>

int main(){
    printf("请分别输入身高的英尺和英寸，如5,7表示5英尺7英寸:");
    int foot; //英尺
    int inch; //英寸
    scanf("%d,%d",&foot,&inch);
    printf("身高是%f米\n",((foot+inch/12)*0.3048));
    return 0;
}
```

运行结果：

![长度换算.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1664098047693-16774fe1-82ed-43f8-9f41-aef606fe0b34.gif#clientId=uecacb1e1-2312-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u83e20e0b&name=%E9%95%BF%E5%BA%A6%E6%8D%A2%E7%AE%97.gif&originHeight=492&originWidth=730&originalType=binary&ratio=1&rotation=0&showTitle=false&size=172684&status=error&style=shadow&taskId=u0c9249c8-6e05-4145-af8e-439ae37c008&title=)

英尺似乎没发挥作用？这是怎么回事？原来，是由于 C 语言中相同数据类型的变量的计算结果仍然是该类型，inch 是 int 类型，12 是整形常量，默认是 int 类型，那么对于这个值永远都是在 0 到 11 范 围的 inch 来说，其与 12 的除法运算永远都是 int 类型，永远都会直接舍弃掉小数点后面的数据，永远都为 0，所以才会有以上的运行结果。

那么，以上程序该如何改进呢？这里，又紧接着引入一个知识点：在 C 语言中不同数据类型的变量的运算，是先将所有变量统一转化为一种表示范围最大的数据类型。

范例：长度换算（改）（修改 length_conversion.c)

```c
#include <stdio.h>

int main(){
    printf("请分别输入身高的英尺和英寸，如5,7表示5英尺7英寸:");
    int foot; //英尺
    int inch; //英寸
    scanf("%d,%d",&foot,&inch);
    printf("身高是%f米\n",((foot+inch/12.0)*0.3048)); //12是整形常量，默认是int类型，12.0是浮点型常量，默认是double类型
    return 0;
}
```

运行结果：

![长度换算（改）.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1664098079136-439b2b83-ca2e-4e29-bdba-01d28f5cd5eb.gif#clientId=uecacb1e1-2312-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u7dfc1547&name=%E9%95%BF%E5%BA%A6%E6%8D%A2%E7%AE%97%EF%BC%88%E6%94%B9%EF%BC%89.gif&originHeight=488&originWidth=731&originalType=binary&ratio=1&rotation=0&showTitle=false&size=177949&status=error&style=shadow&taskId=uf56306c9-6e12-4072-bca6-1f7f3002852&title=)

## 表达式

一个表达式是一系列运算符和算子的组合，用来计算出一个值。运算符（operator）是指进行运算的动作，比如加法运算符”+“，减法运算符”-“，算子（operand）是指参与运算的值，这个值可能是常数、变量和方法返回值等。

## 参考视频

[翁凯 C 语言（bilibili）](https://www.bilibili.com/video/BV19W411B7w1)

[【C 语言】《带你学 C 带你飞》（bilibili）](https://www.bilibili.com/video/BV17s411N78s)
