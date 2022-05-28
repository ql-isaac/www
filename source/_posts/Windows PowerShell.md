---

title: Windows PowerShell

trans: Windows_PowerShell

date: 2022-03-19 22:53:24

updated: 2022-03-19 22:53:24

cover: https://img.imql.life/Windows_PowerShell.png

tags:

- Windows 10 专业版

categories:

- PowerShell

---

[Powershell](https://github.com/PowerShell/PowerShell)——微软拥抱开源的又一力作。

<!-- more -->

## 前言

基于 .NET Framework，2006 年 11 月，Windows PowerShell 1.0 作为可选组件出现在 Windows Server 2008 上，到 2016 年 8 月，Windows PowerShell 5.1 在 Windows 10 周年更新和 Windows Server 2016 中发布，一直到现在，Windows PowerShell 仍然停留在 5.1，如下图，这是为何？

![Windows_PowerShell.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1647703332317-d395ca49-93eb-4583-b5a4-596abaec820d.png#clientId=ub35cbe16-8d60-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u97bcd833&name=Windows_PowerShell.png&originHeight=115&originWidth=548&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5685&status=done&style=none&taskId=ufec539cf-569d-4e8a-af53-42898b29081&title=)

其实微软在这么长的时间里并没有闲着，就在 2018 年 1 月，基于 .NET Core 2.0 构建的开源软件 PowerShell 6.0 发布。

.NET Core，即 .NET Framework 的子集，原来，微软这又是要在开源世界开辟自己的空间了。

如今的 PowerShell 已来到了 7，一个跨平台的任务自动化解决方案，算是真正诞生了，不过我们今天不是要来讲 PowerShell，而是要讲 Windows PowerShell。

## Windows PowerShell 美化

一直以来，Windows 的图形化界面深入人心。在参加工作前，本人对其命令行界面的认识一直停留在 CMD 这个黑乎乎的窗口，而且我也几乎认为这个黑乎乎的窗口什么用也没有，工作后，发现 CMD 还是比较有用的，但是和 Linux 上的 bash 、zsh 和 fish 相比，就显得相形见绌了，至于 Windows PowerShell，我一直是将其与 CMD 画等号的。

微软的又一开源软件——Windows Terminal 的出现让我重新去看待 Windows 的命令行界面，去了解和使用 Windows PowerShell。

如下图，Windows Terminal 让 Windows PowerShell 看起来顺眼了一些，但仍然不够，类似于 bash 、zsh 和 fish，PowerShell 也有自己的 oh-my-xxx 项目——[oh-my-posh](https://github.com/JanDeDobbeleer/oh-my-posh)。

![Windows_Terminal.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1647751443556-3482e034-ff36-401b-991a-a782a898a71b.png#clientId=u05c39fd3-9a6d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u3b8c4106&name=Windows_Terminal.png&originHeight=1078&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25782&status=done&style=none&taskId=udaca32a5-d0b8-4bd2-820a-593e7bf8574&title=)

### 安装 oh-my-posh[[1]](#参考)

1. 利用 PowerShell 命令安装：

```powershell
Install-Module oh-my-posh -Scope CurrentUser
```

2. 提示需要 NuGet，回车以安装并导入：

![需要NuGet.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1647761583429-1cf79630-c1f4-4d36-80a3-92bb25cb4926.png#clientId=u05c39fd3-9a6d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u24cd9a48&name=%E9%9C%80%E8%A6%81NuGet.png&originHeight=195&originWidth=1476&originalType=binary&ratio=1&rotation=0&showTitle=false&size=402160&status=done&style=none&taskId=u8dcf5861-64f8-43a2-9731-eb179b682cf&title=)

3. 输入 Y 以确定从“PSGallery”安装模块：

![确认.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1647761830158-cad4c1b1-e080-44b3-b827-66aefb0de647.png#clientId=u05c39fd3-9a6d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u66c24aeb&name=%E7%A1%AE%E8%AE%A4.png&originHeight=98&originWidth=1478&originalType=binary&ratio=1&rotation=0&showTitle=false&size=175381&status=done&style=none&taskId=uac247691-05d9-49b7-b8d4-1fcaeb3bbbe&title=)

### 安装 **Nerd Fonts(Hack)**

[前往 Nerd Fonts 发布页面](https://github.com/ryanoasis/nerd-fonts/releases/)，我下载的是 v2.1.0 的 Hack 字体。

下载好后解压，这里有许多版本的 Hack，要选 Windows Compatible 的， 我就装个 Hack Regular Nerd Font Complete Windows Compatible 吧，直接双击安装即可。

### 设置字体

重新进入 Windows PowerShell，找到 Windows PowerShell 的字体设置，如下图，选择 Hack NF，保存。

![字体.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1647769154227-504b3bb9-0649-4399-a021-3cbbfb91f25f.png#clientId=u05c39fd3-9a6d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ue7e5a4a7&name=%E5%AD%97%E4%BD%93.png&originHeight=785&originWidth=1481&originalType=binary&ratio=1&rotation=0&showTitle=false&size=499233&status=done&style=none&taskId=u894178fe-d16f-445b-b260-3eefee33153&title=)

### 安装 posh-git

利用 PowerShell 命令安装：

```powershell
Install-Module posh-git -Scope CurrentUser
```

同样输入 Y 以确定从“PSGallery”安装模块。

### 编辑 PowerShell 配置文件

记事本打开配置文件：

```powershell
notepad.exe $PROFILE
```

还不存在此文件，选择创建：

![PROFILE.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1647765910089-c92b04c6-5b73-41b7-b613-1aedd0b22bbc.png#clientId=u05c39fd3-9a6d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ucd05b8bb&name=PROFILE.png&originHeight=273&originWidth=549&originalType=binary&ratio=1&rotation=0&showTitle=false&size=8084&status=done&style=none&taskId=ubda56938-aa3a-4b67-a1af-b8abf52a7da&title=)

编辑配置文件：

```diff
+Import-Module posh-git
+Import-Module oh-my-posh
+Set-PoshPrompt -Theme clean-detailed
```

{% note info %}

以上`-Theme`后面指定自己喜欢的主题，[主题列表见此](https://ohmyposh.dev/docs/themes)。

{% endnote %}

### 设置 PowerShell 执行策略[[2]](#参考)

一般此时重新进入 Windows PowerShell 就能看到已经美化好了，但是结果是：

![Execution_Policies.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1647767054839-5ae817cd-392d-4cb4-80c3-e4bfd6837475.png#clientId=u05c39fd3-9a6d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ud3655b5b&name=Execution_Policies.png&originHeight=296&originWidth=1531&originalType=binary&ratio=1&rotation=0&showTitle=false&size=455866&status=done&style=none&taskId=u6d39a6b1-28cf-4818-8e6b-f29d66b16cd&title=)

以上红字提示的参阅地址中有解决办法，原来默认的执行策略为 Restricted，如下图。

![Restricted.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1647767310640-8da96ffd-f5c4-41a5-a140-9fbdcf379828.png#clientId=u05c39fd3-9a6d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u4e428cf6&name=Restricted.png&originHeight=50&originWidth=619&originalType=binary&ratio=1&rotation=0&showTitle=false&size=31343&status=done&style=none&taskId=u7ba8a21e-fb53-4994-9e25-3fd7f94327a&title=)

我们设置执行策略为 RemoteSigned：

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

再重新进入 Windows PowerShell（一开始需要进行导入，可能有点慢），美化完成。

### 参考

1. [在 Windows 上 安装 Oh My Posh](https://ohmyposh.dev/docs/) [↩](#安装-oh-my-posh-1)
1. [about_Execution_Policies](https://docs.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-5.1) [↩](#设置-PowerShell-执行策略-2)

- [2021 年打开 Powershell 的正确姿势：）](https://www.bilibili.com/video/BV1jQ4y1Y7mG)
- [配置一个漂亮的 Windows Powershell (1)](https://www.bilibili.com/video/BV12u411Z7Zo)
