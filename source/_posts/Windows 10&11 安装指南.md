---
title: Windows 10&11 安装指南
trans: The_Installation_Guide_of_Windows_10_and_Windows_11
date: 2022-04-20 19:42:00
updated: 2022-04-20 19:42:00
cover: https://img.imql.life/The_Installation_Guide_of_Windows_10_and_Windows_11.png
top_img: false
tags:
  - Windows 10 专业版
  - Windows 11 专业版

categories:
  - PC
---

还不会安装 Windows？快点进来！

<!-- more -->

## 下载系统镜像

两个下载渠道：[微软官网](https://www.microsoft.com/zh-cn/software-download)和 [I Tell You（新版）](https://next.itellyou.cn)，推荐 I Tell You （新版），这是一个提供原版软件下载链接的网站，下载工具的话就推荐[迅雷](https://www.xunlei.com/index.html)。我选择的 Windows 10 和 Window 11 镜像分别为：
![Windows_10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651659560634-78c2b510-72e4-4a6c-9b50-095436828f0f.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8605fecb&name=Windows_10.png&originHeight=943&originWidth=1418&originalType=binary&ratio=1&rotation=0&showTitle=false&size=543635&status=done&style=shadow&taskId=uabce3a81-9989-492a-a6a0-fea62a6d852&title=)![Windows_11.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651659895743-51419d41-657f-4dd9-91fa-f918dc44d301.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u510bfd37&name=Windows_11.png&originHeight=918&originWidth=1405&originalType=binary&ratio=1&rotation=0&showTitle=false&size=511058&status=done&style=shadow&taskId=u3727d541-53b2-42f4-98ac-9a48eb9316c&title=)
直接点击复制右边的下载链接（建议 BT），如果此时你的迅雷正在运行中的话，此时会自动解析种子并提示下载，如下图，速度还是很快的。
![速度很快.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651660159504-f3ae79ef-bf41-4371-9a45-14a316af39f6.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ua8fd8adc&name=%E9%80%9F%E5%BA%A6%E5%BE%88%E5%BF%AB.png&originHeight=850&originWidth=1400&originalType=binary&ratio=1&rotation=0&showTitle=false&size=243272&status=done&style=shadow&taskId=u92d0368e-0afc-4e69-8dba-97df00c9eca&title=)
下载完成后勾选一下显示校验信息：
![Windows_10校验码.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651661009433-b5600158-a04c-41ab-8f18-d14018fb2bf5.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u11711454&name=Windows_10%E6%A0%A1%E9%AA%8C%E7%A0%81.png&originHeight=939&originWidth=1401&originalType=binary&ratio=1&rotation=0&showTitle=false&size=426210&status=done&style=shadow&taskId=ub1a95fb1-135e-4eb3-bdc6-7cf4e5d8ab0&title=)![Windows_11校验码.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651661179018-fdbd3357-2097-43ba-ab3f-0ad87dea1250.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u19772640&name=Windows_11%E6%A0%A1%E9%AA%8C%E7%A0%81.png&originHeight=938&originWidth=1406&originalType=binary&ratio=1&rotation=0&showTitle=false&size=352472&status=done&style=shadow&taskId=u2ccb9c90-4ce0-4a5c-b606-fc95ae4f347&title=)
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
![Windows_11安装要求.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1653192899024-76e7ce80-be4d-4db8-b1d1-314d8099b8da.png#clientId=ucd30f78d-a95b-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u264eb435&name=Windows_11%E5%AE%89%E8%A3%85%E8%A6%81%E6%B1%82.png&originHeight=553&originWidth=700&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24051&status=done&style=shadow&taskId=uae901a8b-3806-4132-a098-21c2787d3cc&title=)
{% note info %}
直接安装 Windows 10/11 步骤一致，下面以 Windows 10 为例说明。
{% endnote %}
首先确保下载的镜像不在 C 盘，如果原来的操作系统是 Windows 7 之后的系统，直接双击打开镜像文件。
如果原来的操作系统为 Windwos 7，是不能直接双击打开镜像文件的，需要使用解压缩工具将镜像文件解压出来，例如使用 7z。
双击运行 setup.exe。
首先是提示你是否要对现在的镜像文件进行更新，建议这里选择更改 Windows 安装程序下载更新的方式：
![更改安装程序下载更新的方式.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1653193005835-83d5cd4b-2324-4c13-823c-cdcf06b905c5.png#clientId=ucd30f78d-a95b-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ud862c938&name=%E6%9B%B4%E6%94%B9%E5%AE%89%E8%A3%85%E7%A8%8B%E5%BA%8F%E4%B8%8B%E8%BD%BD%E6%9B%B4%E6%96%B0%E7%9A%84%E6%96%B9%E5%BC%8F.png&originHeight=552&originWidth=700&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23462&status=done&style=shadow&taskId=u2f066937-21b0-4be9-87a0-8409343451e&title=)
选择不是现在，下一步（要是现在更新的话就需要等较长时间）：
![不是现在.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1653193063078-bf88bed3-365d-4c00-9991-04e7b12de126.png#clientId=ucd30f78d-a95b-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u9a88c2e0&name=%E4%B8%8D%E6%98%AF%E7%8E%B0%E5%9C%A8.png&originHeight=552&originWidth=700&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28965&status=done&style=shadow&taskId=u0cde076a-0621-4e0a-952c-13e0a41ab96&title=)
检查准备中：
![检查准备中.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651929570183-87074aba-6c4b-412d-bc3e-d40d7c2df046.png#clientId=uf28cda61-edb0-4&crop=0&crop=0.0656&crop=1&crop=1&from=paste&height=442&id=u909ec9cc&name=%E6%A3%80%E6%9F%A5%E5%87%86%E5%A4%87%E4%B8%AD.png&originHeight=553&originWidth=700&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9632&status=done&style=shadow&taskId=uf52c8e7c-72f2-4999-bf49-cc43b118920&title=&width=560)
选择版本，我这里选择专业版：
![Windows_10专业版.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1653193158819-3475e366-f261-4b5e-afb4-d928c51206fb.png#clientId=ucd30f78d-a95b-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uc8325dc7&name=Windows_10%E4%B8%93%E4%B8%9A%E7%89%88.png&originHeight=444&originWidth=800&originalType=binary&ratio=1&rotation=0&showTitle=false&size=15959&status=done&style=shadow&taskId=u9fd3791e-ba44-41d5-a677-8e847bfae2d&title=)
接受条款：
![接受条款.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1653193303235-180773fc-25c6-4ed0-9120-b159c95c4a68.png#clientId=ucd30f78d-a95b-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8c53764f&name=%E6%8E%A5%E5%8F%97%E6%9D%A1%E6%AC%BE.png&originHeight=553&originWidth=700&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20018&status=done&style=shadow&taskId=u20091a91-83ca-44cb-8d94-7571172b594&title=)
最后的准备：
![最后的准备.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651929833265-e34e0788-a74f-4480-b193-e6264b68280f.png#clientId=uf28cda61-edb0-4&crop=0&crop=0.0519&crop=1&crop=1&from=paste&height=443&id=u95e11105&name=%E6%9C%80%E5%90%8E%E7%9A%84%E5%87%86%E5%A4%87.png&originHeight=554&originWidth=700&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13040&status=done&style=shadow&taskId=uf73faea4-0ce2-4f42-8d44-36261a48732&title=&width=560)
这里就默认保留个人文件和应用，也就是仅仅操作系统会被改变，C 盘中的个人文件和应用会被保留，可以自行更改要保留的内容。
![保留个人文件和应用.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1653193522992-60c5719a-8ab7-48a7-9fd5-9722e8981a26.png#clientId=ucd30f78d-a95b-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ubcc5ca76&name=%E4%BF%9D%E7%95%99%E4%B8%AA%E4%BA%BA%E6%96%87%E4%BB%B6%E5%92%8C%E5%BA%94%E7%94%A8.png&originHeight=552&originWidth=700&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20361&status=done&style=shadow&taskId=u9e7def5d-7cf2-4f4a-b469-dd91fcc85c4&title=)
{% note warning %}
升级跨度比较大的话这里只能保留 C 盘中的个人文件。
{% endnote %}
开始安装，等待即可。

## 方法二：从 U 盘启动安装

{% note success %}
适用情况：刚组装了一台台式机，还没有操作系统；电脑进不去了，C 盘没什么文件，可以直接格式化。
{% endnote %}
空 U 盘插入到一台正常使用的电脑上，使用 [Rufus](https://rufus.ie/) 制作启动盘：
![制作.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651663609040-eeb75f62-6ede-46e0-9f45-a0fdcae4ae6b.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u74261633&name=%E5%88%B6%E4%BD%9C.png&originHeight=758&originWidth=481&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1461590&status=done&style=shadow&taskId=u97d916b9-5a69-4e07-b75d-0cff6b7937e&title=)
在制作 Windows 11 安装 U 盘时，注意到镜像选项处有两个特别的选项，如下图，简单理解就是一个会去检查是否支持 TPM 2.0，一个不会。
![需要TPM2.0.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1653193606115-08ee5ad1-4482-4411-9f43-a3d94329a7fa.png#clientId=ue905bb14-f39c-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uca5d64a5&name=%E9%9C%80%E8%A6%81TPM2.0.png&originHeight=751&originWidth=475&originalType=binary&ratio=1&rotation=0&showTitle=false&size=34676&status=done&style=shadow&taskId=u60608b93-4cd2-405a-958c-0b2a7c453d8&title=)
![不需要TPM2.0.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1653193654993-3b22bb5a-7dc2-4b66-8c43-53a51c882f30.png#clientId=ue905bb14-f39c-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uc09abd0e&name=%E4%B8%8D%E9%9C%80%E8%A6%81TPM2.0.png&originHeight=751&originWidth=475&originalType=binary&ratio=1&rotation=0&showTitle=false&size=34548&status=done&style=shadow&taskId=u0e85fa55-1dca-4332-9656-fa4d9ea7c6d&title=)
制作完成后就可以将安装盘插到要安装的机器上，启动电脑，同时不停按 F2 进入 BIOS，确认引导模式为 UEFI。
F10 保存退出 BIOS，同时不停按 F12 进入启动项选择界面。键盘上下键选择带“EFI”“USB”字样的，一般是第二个，回车。
下一步：
![下一步.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651666953977-0aae1d40-08e7-40af-af04-337c1d4e6c8e.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u38744114&name=%E4%B8%8B%E4%B8%80%E6%AD%A5.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18721&status=done&style=shadow&taskId=ucfb34257-a8a5-4c59-8119-997a9b86734&title=)
现在安装：
![现在安装.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651666985512-1d2f7446-2a36-4060-b140-d74e8d6eb5ac.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u135784e0&name=%E7%8E%B0%E5%9C%A8%E5%AE%89%E8%A3%85.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=14823&status=done&style=shadow&taskId=u30fe95ae-321c-4116-9abe-9c5c2d47034&title=)
选择要安装的 Windows 10/11，我这里选择专业版：
![选择要安装的Windows_10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652000625203-c323b6a7-cc04-40f8-9117-f055711282c8.png#clientId=u25500315-2f03-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u90542401&name=%E9%80%89%E6%8B%A9%E8%A6%81%E5%AE%89%E8%A3%85%E7%9A%84Windows_10.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23201&status=done&style=shadow&taskId=u817af7f7-49f9-43f6-9621-4ec0c076b4e&title=)
![选择要安装的Windows_11.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652000584813-28f10e4a-63bd-46a0-a857-f752eaa9823a.png#clientId=u25500315-2f03-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=udb94d5d8&name=%E9%80%89%E6%8B%A9%E8%A6%81%E5%AE%89%E8%A3%85%E7%9A%84Windows_11.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=21648&status=done&style=shadow&taskId=u27ebef8e-1cce-4c8b-a997-470c44f6fab&title=)
接受：
![接受.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651667177546-d4f61cb9-33be-47e7-859c-e00fcb967923.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u18ec5031&name=%E6%8E%A5%E5%8F%97.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25455&status=done&style=shadow&taskId=u822cb7ec-b3ff-41ab-a816-1eecf0fe9c8&title=)
自定义安装：
![自定义安装.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651667319040-bd584284-e875-46ee-80fc-990d068621f5.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u05ddd54f&name=%E8%87%AA%E5%AE%9A%E4%B9%89%E5%AE%89%E8%A3%85.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25204&status=done&style=shadow&taskId=u26f72a5f-903c-4fa0-bb4b-05772c56ebd&title=)
上图中如果选择升级安装，会有下面的提示。
![升级选项不可用.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651667466406-0ce1099d-b028-4020-b177-5ecd982d7d7a.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uf6a4ada6&name=%E5%8D%87%E7%BA%A7%E9%80%89%E9%A1%B9%E4%B8%8D%E5%8F%AF%E7%94%A8.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23407&status=done&style=shadow&taskId=u53bbbb5d-91f9-41f6-b866-0e3ae1fd24b&title=)
如果这是一台新机器，还没有安装操作系统，那么选择未分配空间的驱动器，选择新建，设定 C 盘大小，应用，确定：
{% note info %}
C 盘大小建议设定为 50-100GB。
{% endnote %}
![驱动器0.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651668483942-c42b7eca-c1bb-448f-9402-82d3ca4321cf.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u84881da0&name=%E9%A9%B1%E5%8A%A8%E5%99%A80.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=42267&status=done&style=shadow&taskId=u448df626-86ae-408d-842a-c8affc67827&title=)
接着依次划分剩余的未分配空间给 D 盘、E 盘等盘。
如果这是一台旧机器，C 盘上安装过操作系统，但是 C 盘没什么文件，可以直接格式化，那么我们依次删除前三个驱动器分区：
![前三个驱动器分区.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651669186168-cb3a099b-3c79-4f5e-963d-ec9957045ebc.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u363d1ea7&name=%E5%89%8D%E4%B8%89%E4%B8%AA%E9%A9%B1%E5%8A%A8%E5%99%A8%E5%88%86%E5%8C%BA.png&originHeight=350&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=19117&status=done&style=shadow&taskId=u1316c250-2b84-4bc8-861b-4613a175332&title=)
![删除分区1.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651669063487-32307c18-690a-4d1f-9bce-b77683f3ed87.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u72685fab&name=%E5%88%A0%E9%99%A4%E5%88%86%E5%8C%BA1.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=44335&status=done&style=shadow&taskId=u03981833-0955-45a3-81af-19bf96eb446&title=)
![删除分区2.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651669143415-df7e3741-1493-42a1-9fcf-cd1f02ec0505.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u12c1eaa5&name=%E5%88%A0%E9%99%A4%E5%88%86%E5%8C%BA2.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=47958&status=done&style=shadow&taskId=u807524fb-78f9-4f7a-b465-932d324d86c&title=)
![删除分区3.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651669236956-4707fb87-dab8-44db-aced-f2d95639fbce.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uacfd0aa9&name=%E5%88%A0%E9%99%A4%E5%88%86%E5%8C%BA3.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=44719&status=done&style=shadow&taskId=u3534baa5-1694-450e-b5f1-bae766fc73b&title=)
这里有可能只有两个驱动器分区需要删除：
![前两个驱动器分区.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1656856044344-039848eb-e12e-444f-b7e3-4753606f2ced.png#clientId=ud6b5db4f-65fc-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u96be2b02&name=%E5%89%8D%E4%B8%A4%E4%B8%AA%E9%A9%B1%E5%8A%A8%E5%99%A8%E5%88%86%E5%8C%BA.png&originHeight=354&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16723&status=done&style=shadow&taskId=uc599162f-fe5a-48c5-bd1c-cf0adb608cb&title=)
接下来就和上述机器还没有安装操作系统的情况一样，选择未分配空间的驱动器，新建 C 盘、D 盘和 E 盘等盘。
选择新建的 C 盘（第一个类型为主分区的分区），下一步：
![下一步.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651670587270-5e7dd40b-0258-4ea9-8114-601becf882a6.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u64a3182b&name=%E4%B8%8B%E4%B8%80%E6%AD%A5.png&originHeight=350&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=19121&status=done&style=shadow&taskId=u00316862-ef71-4796-96fd-13f34a0fccc&title=)
安装中，等待即可：
![安装中.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1651670657474-4b65b90e-9da2-4c7b-a7a0-10097ed03459.png#clientId=u2d1b3fe9-8ada-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u83558058&name=%E5%AE%89%E8%A3%85%E4%B8%AD.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16262&status=done&style=shadow&taskId=ueee0768b-0bc4-40fe-a43b-d133ae43d71&title=)

## 方法三：在 PE 中安装

{% note info %}
PE，即预安装环境，是带有有限服务的最小 Windows，在 PE 中安装 Windows 是最好的 Windows 安装办法。
{% endnote %}

### 制作 PE

首先需要一个 U 盘，最好容量大一下，这样可以放下多个镜像，许多其他软件，满足各种安装需要。制作 PE 的软件比较多，强烈推荐[微 PE](https://www.wepe.com.cn/) 和[优启通](https://www.upe.net/)，我这里以优启通为例。
运行优启通，选择磁盘，全新制作：
![优启通.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652611714998-88aab7ff-7b9d-4c37-84c5-f677fc85e966.png#clientId=u48142328-cb64-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uc6d0a530&name=%E4%BC%98%E5%90%AF%E9%80%9A.png&originHeight=500&originWidth=728&originalType=binary&ratio=1&rotation=0&showTitle=false&size=62970&status=done&style=shadow&taskId=ub5810b1d-d007-4311-bc15-4722dc2b0f2&title=)
制作完成后就可以将 PE 盘插到要安装的机器上，启动电脑，同时不停按 F2 进入 BIOS，确认引导模式为 UEFI。
F10 保存退出 BIOS，同时不停按 F12 进入启动项选择界面。键盘上下键选择带“EFI”“USB”字样的，一般是第二个，回车。

### 备份 C 盘文件（可选）

看下自己的 C 盘有没有重要文件，一般就是桌面和下载中的文件，考虑转移一下。

### 硬盘分区（可选）

对于新的机器，或者整个硬盘数据可清除的情况，可通过桌面上的 DG 硬盘分区对硬盘分好区。
选择好硬盘，选择上方的快速分区，注意分区表类型选择 GUID，分区数目自定义，其他的推荐默认就好，确定：
![硬盘分区.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652615567099-39c6ad96-3b70-483b-9d60-af8297c77cab.png#clientId=u48142328-cb64-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uc2116cad&name=%E7%A1%AC%E7%9B%98%E5%88%86%E5%8C%BA.png&originHeight=468&originWidth=686&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18742&status=done&style=shadow&taskId=u7fad30b7-e4c9-45d2-bcba-43849094a18&title=)

### 安装

可直接双击镜像文件安装，之后的步骤同从 U 盘启动安装，也可选择桌面上的 EIX 系统安装进行安装。
左侧选择版本，右侧选择系统盘（注意在 PE 中，系统盘不一定为 C 盘，请以实际系统盘盘符为准），点击一键恢复，确认：
![映像恢复.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652616740965-39e1a03f-3e62-49d6-8c0a-adff34c1f2f3.png#clientId=u48142328-cb64-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uf93e0794&name=%E6%98%A0%E5%83%8F%E6%81%A2%E5%A4%8D.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=84707&status=done&style=shadow&taskId=u26c0d6ad-1788-4311-9cea-5a6da9f7649&title=)
![确认.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652616891741-7dcb9511-9bc0-4a07-8421-99447fa48f25.png#clientId=u48142328-cb64-4&crop=0.0028&crop=0.0033&crop=1&crop=1&from=drop&height=303&id=u0c70b140&name=%E7%A1%AE%E8%AE%A4.png&originHeight=304&originWidth=360&originalType=binary&ratio=1&rotation=0&showTitle=false&size=14355&status=done&style=shadow&taskId=u8a2535e0-b462-4186-8066-9c3071e9a14&title=&width=359)
恢复中，等待即可：
![恢复中.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652617017317-6311a68c-1bbc-4d10-87db-128a38cedc56.png#clientId=u48142328-cb64-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ud8d6b1dc&name=%E6%81%A2%E5%A4%8D%E4%B8%AD.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=94337&status=done&style=shadow&taskId=u3b2677a9-de9a-42b3-bdef-6bfbb6467af&title=)

## 开箱体验（OOBE）

OOBE（Out-of-box experience），即开箱体验，它是在安装完 Windows 后要做的第一件事，以下为 Windows 10/11 的演示。

### Windows 10

区域设置：
![中国-Windows10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538392392-3322d42d-f3f3-47a2-a109-55672a9f4294.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u9120e9e4&name=%E4%B8%AD%E5%9B%BD-Windows10.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24022&status=done&style=shadow&taskId=u4a9e96a4-1599-47d0-b117-d9d087fc0fa&title=)
输入法：
![微软拼音-Windows10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652537798009-3758dfd8-c170-45e2-82cd-8a4e35df0b05.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ubeb27a3b&name=%E5%BE%AE%E8%BD%AF%E6%8B%BC%E9%9F%B3-Windows10.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18232&status=done&style=shadow&taskId=uba37b625-5387-49ae-87db-7fe2cd9ed1b&title=)
添加第二种键盘布局：
![跳过-Windows10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652537857599-c97b7d4a-867d-461f-a713-bdedad9e42c7.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ub0e60b7d&name=%E8%B7%B3%E8%BF%87-Windows10.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20049&status=done&style=shadow&taskId=ub8e190ef-ac46-42c5-ba54-529bd9ec857&title=)
连接到网络：
![我没有Internet连接-Windows10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538018165-3318a416-bb86-4790-8db9-5ee819707b6f.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u7d0b89d5&name=%E6%88%91%E6%B2%A1%E6%9C%89Internet%E8%BF%9E%E6%8E%A5-Windows10.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=14506&status=done&style=shadow&taskId=uae178121-6c83-49d7-bb29-4206e27a507&title=)
创建用户：
![创建用户-Windows10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538190279-75c510e2-fdba-403e-8a6e-6bff6620048a.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u98890ea7&name=%E5%88%9B%E5%BB%BA%E7%94%A8%E6%88%B7-Windows10.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=22012&status=done&style=shadow&taskId=ue7d82002-37d5-4f21-85a1-8a768e04c65&title=)
设置密码：
![设置密码-Windows10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538225072-2b67f48d-b62f-411e-8b72-e45e4f2d5afb.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u96d74a3a&name=%E8%AE%BE%E7%BD%AE%E5%AF%86%E7%A0%81-Windows10.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=22250&status=done&style=shadow&taskId=uca876d54-ca9c-4bee-9ed0-612f57ce35f&title=)
隐私设置：
![隐私设置-Windows10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538252509-83130498-1be8-4e36-9d60-491423782141.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uf5c79f4b&name=%E9%9A%90%E7%A7%81%E8%AE%BE%E7%BD%AE-Windows10.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=72278&status=done&style=shadow&taskId=u3efeb6ca-7be7-4a6a-9792-7b1fd05a4df&title=)
微软小娜：
![微软小娜-Windows10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538278031-64088851-651d-4c38-9444-89386765c6c6.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u9498b221&name=%E5%BE%AE%E8%BD%AF%E5%B0%8F%E5%A8%9C-Windows10.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=71355&status=done&style=shadow&taskId=u90620a71-da17-4c26-ae84-4d06519e0cb&title=)
即将完毕：
![即将完毕-Windows10.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538325416-24b2220b-8d26-4774-851e-8417f7f71b4c.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8ecb6b87&name=%E5%8D%B3%E5%B0%86%E5%AE%8C%E6%AF%95-Windows10.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13070&status=done&style=shadow&taskId=u170396ca-1ebd-49b2-bf2f-5d2ef2f827c&title=)

### Windows 11

区域设置：
![中国-Windows11.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538491495-71e657eb-7be2-4a18-9029-7e84bc9f8415.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u3dcf6a28&name=%E4%B8%AD%E5%9B%BD-Windows11.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=176519&status=done&style=shadow&taskId=u2bbb9ace-53e4-4d07-966d-8c8b0e12fa2&title=)
输入法：
![微软拼音-Windows11.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538568726-88f7bbad-231f-44e7-a945-a18a718f2ce3.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u149d6bc2&name=%E5%BE%AE%E8%BD%AF%E6%8B%BC%E9%9F%B3-Windows11.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=168102&status=done&style=shadow&taskId=u5c8b2263-040d-4d42-a0e9-f36bae9de56&title=)
添加第二种键盘布局：
![跳过-Windows11.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538624015-ab78e45e-d4a6-47d6-a67b-9b627759b696.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u1b9e32ca&name=%E8%B7%B3%E8%BF%87-Windows11.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=167249&status=done&style=shadow&taskId=u578a0f6b-ba2b-4681-966f-8b688f964d4&title=)
连接到网络：
![我没有Internet连接-Windows11.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538675625-714f690e-e247-4660-b269-eac664eb0790.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u9a6b0c74&name=%E6%88%91%E6%B2%A1%E6%9C%89Internet%E8%BF%9E%E6%8E%A5-Windows11.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=176289&status=done&style=shadow&taskId=ud5be2af2-2eb3-4b1e-b8ee-0f7bcc50823&title=)
创建用户：
![创建用户-Windows11.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538760477-ea30ed40-c4e1-4e94-a75f-9e2ce44a394a.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ua17c48c6&name=%E5%88%9B%E5%BB%BA%E7%94%A8%E6%88%B7-Windows11.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=166728&status=done&style=shadow&taskId=ue69bbf98-1a8d-4ec3-961f-4747b9fa60a&title=)
设置密码：
![设置密码-Windows11.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538876217-61d01af8-3651-4494-8734-df7f197a6126.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uc3f12f0e&name=%E8%AE%BE%E7%BD%AE%E5%AF%86%E7%A0%81-Windows11.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=167293&status=done&style=shadow&taskId=u4bf30355-af93-40af-8f12-df5dcfe5d35&title=)
隐私设置：
![隐私设置-Windows11.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652538936125-62d615f3-def3-499c-a3fd-144ba47acc60.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u6feb1400&name=%E9%9A%90%E7%A7%81%E8%AE%BE%E7%BD%AE-Windows11.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=203694&status=done&style=shadow&taskId=u5a2549c7-c69f-4f87-9355-b0a92eaa43e&title=)
即将完毕：
![即将完毕-Windows11.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1652539030460-a8d70f98-b896-43d6-aeda-7d3217c86781.png#clientId=u7af6d2bf-6034-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u690e558e&name=%E5%8D%B3%E5%B0%86%E5%AE%8C%E6%AF%95-Windows11.png&originHeight=768&originWidth=1024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=188518&status=done&style=shadow&taskId=u69fe2e15-84cf-4b0d-8e7b-69628e53065&title=)
