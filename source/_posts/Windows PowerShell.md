---
title: Windows PowerShell
urlname: yw8hhb
date: "2022-03-19 22:53:24"
updated: "2022-03-19 22:53:24"
trans: Windows_PowerShell
cover: "https://img.imql.life/Windows_PowerShell.png"
categories:
  - Windows PowerShell
---

[Powershell](https://github.com/PowerShell/PowerShell)——微软拥抱开源的又一力作。

<!-- more -->

## 前言

基于 .NET Framework，2006 年 11 月，Windows PowerShell 1.0 作为可选组件出现在 Windows Server 2008 上，到 2016 年 8 月，Windows PowerShell 5.1 在 Windows 10 周年更新和 Windows Server 2016 中发布，一直到现在，Windows PowerShell 仍然停留在 5.1，如下图，这是为何？
![Windows_PowerShell.png](https://img.imql.life/illustrations/f0bd31264a4123e055441e3074f98dd7.png)
其实微软在这么长的时间里并没有闲着，就在 2018 年 1 月，基于 .NET Core 2.0 构建的开源软件 PowerShell 6.0 发布。
.NET Core，即 .NET Framework 的子集，原来，微软这又是要在开源世界开辟自己的空间了。
如今的 PowerShell 已来到了 7，一个跨平台的任务自动化解决方案，算是真正诞生了，不过我们今天不是要来讲 PowerShell，而是要讲 Windows PowerShell。

## Windows PowerShell 美化

一直以来，Windows 的图形化界面深入人心。在参加工作前，本人对其命令行界面的认识一直停留在 CMD 这个黑乎乎的窗口，而且我也几乎认为这个黑乎乎的窗口什么用也没有，工作后，发现 CMD 还是比较有用的，但是和 Linux 上的 bash 、zsh 和 fish 相比，就显得相形见绌了，至于 Windows PowerShell，我一直是将其与 CMD 画等号的。
微软的又一开源软件——Windows Terminal 的出现让我重新去看待 Windows 的命令行界面，去了解和使用 Windows PowerShell。
如下图，Windows Terminal 让 Windows PowerShell 看起来顺眼了一些，但仍然不够，类似于 bash 、zsh 和 fish，PowerShell 也有自己的 oh-my-xxx 项目——[oh-my-posh](https://github.com/JanDeDobbeleer/oh-my-posh)。
![Windows_Terminal.png](https://img.imql.life/illustrations/559cef53152f46e7df50f7da185e92bb.png)

### 安装 oh-my-posh[^1]

1. 利用 PowerShell 命令安装：

```powershell
Install-Module oh-my-posh -Scope CurrentUser
```

2. 提示需要 NuGet，回车以安装并导入：

![需要NuGet.png](https://img.imql.life/illustrations/2857dad2e859dd791a7781d464e71d12.png)

3. 输入 Y 以确定从“PSGallery”安装模块：

![确认.png](https://img.imql.life/illustrations/04e98fe12f8276d06f666db93fdeb2cb.png)

### 安装 **Nerd Fonts(Hack)**

[前往 Nerd Fonts 发布页面](https://github.com/ryanoasis/nerd-fonts/releases/)，我下载的是 v2.1.0 的 Hack 字体。
下载好后解压，这里有许多版本的 Hack，要选 Windows Compatible 的， 我就装个 Hack Regular Nerd Font Complete Windows Compatible 吧，直接双击安装即可。

### 设置字体

重新进入 Windows PowerShell，找到 Windows PowerShell 的字体设置，如下图，选择 Hack NF，保存。
![字体.png](https://img.imql.life/illustrations/d27c853079204309f601c3d19b0a19db.png)

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
![PROFILE.png](https://img.imql.life/illustrations/90db2c3f829eb7bbe9e68ad17d63d20f.png)
编辑配置文件：

```diff
+Import-Module posh-git
+Import-Module oh-my-posh
+Set-PoshPrompt -Theme clean-detailed
```

{% note info %}
以上`-Theme`后面指定自己喜欢的主题，[主题列表见此](https://ohmyposh.dev/docs/themes)。
{% endnote %}

### 设置 PowerShell 执行策略[^2]

一般此时重新进入 Windows PowerShell 就能看到已经美化好了，但是结果是：
![Execution_Policies.png](https://img.imql.life/illustrations/f107ea7bc2a09ef8e8340886a0a4ce40.png)
以上红字提示的参阅地址中有解决办法，原来默认的执行策略为 Restricted，如下图。
![Restricted.png](https://img.imql.life/illustrations/370d106359bc6d0dfe2016c361e5bf83.png)
我们设置执行策略为 RemoteSigned：

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

再重新进入 Windows PowerShell（一开始需要进行导入，可能有点慢），美化完成。

## 参考

- [2021 年打开 Powershell 的正确姿势：）](https://www.bilibili.com/video/BV1jQ4y1Y7mG)
- [配置一个漂亮的 Windows Powershell (1)](https://www.bilibili.com/video/BV12u411Z7Zo)

[^1]: [在 Windows 上 安装 Oh My Posh](https://ohmyposh.dev/docs/)
[^2]: [about_Execution_Policies](https://docs.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-5.1) [↩](#设置-PowerShell-执行策略-2)
