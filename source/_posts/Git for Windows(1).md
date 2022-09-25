---

title: Git for Windows(1)

trans: Git_for_Windows_1

date: 2021-01-03 15:27:43

cover: https://img.imql.life/Git_for_Windows.jpg

categories:

- Git for Windows

---

来记录一下 Git for Windows 的使用。

<!-- more -->

每次打开 VS Code 时右下角总提示这个，还是更新一下吧，直接点击更新 GIT。

![](https://img.imql.life/illustrations/FgL5gx1r5FIWsBq4aFPnR-GJ9K4C.png)

原来是跳转到 Git 官网。

![](https://img.imql.life/illustrations/FsXPePDtVVQxSGmlpdOKDnyJKC3W.png)

这里会跳转到 IE 浏览器，呵呵，赶紧到 Windows 的所有设置-应用-默认应用中把 Web 浏览器设置成 Microsoft Edge 再打开 Git 官网。

![](https://img.imql.life/illustrations/Fn30Bp8CMTd4lGE8Kk3kLMNubsRO.png)

常规操作：下载，双击安装。

![](https://img.imql.life/illustrations/FkmowB0CZo0wxUas9KPKrco_z8Se.png)

Only show new option，嗯，很人性化！好评！

![](https://img.imql.life/illustrations/FtFRTazWp1Y8qVEAyBdmlPDFbnKa.png)

勾选第二个，以后用`git init`初始化仓库时默认分支名就为 main 了。

{% note info %}

由于某些原因，2020 年 10 月 1 日，GitHub 将启用 main 作为默认分支名，master 将成为历史！

{% endnote %}

![](https://img.imql.life/illustrations/FhumugdJG6XRP8w_X_lOYT6f2g4a.png)

这个直接 Next，默认即可。

![](https://img.imql.life/illustrations/FoauVM2a8i-WvNls2raHGopdlyyo.png)

credential helper，凭据帮助器？这是个什么玩意儿？star 一下这个[cross-platform version of the Git Credential Manager](https://github.com/microsoft/Git-Credential-Manager-Core)先，有时间看看（虽然看不懂）。

![](https://img.imql.life/illustrations/FtJbfHT2PB7Vrh8vFoVRK_IyWDM5.png)

实验性的选项：允许在 Git Bash 窗口中运行原生控制台程序，如 Node 或 Python，而不使用 winpty，但它仍然有已知的 bug，不勾选。

![](https://img.imql.life/illustrations/FnCZrqV9ZKndmb9X7dZ5afRfpQi4.png)

安装中：

![](https://img.imql.life/illustrations/FjTB7uAF0uFwgVyRpTI-ojwUfFIg.png)

完成：

![](https://img.imql.life/illustrations/FmWzvInvG9D5Q88a6NYsgIbt9aLV.png)

Release Notes：

![](https://img.imql.life/illustrations/Fjz6IdAWqm0vio87duHXKCJchXLH.png)
