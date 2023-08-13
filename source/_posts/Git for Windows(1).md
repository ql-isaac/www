---
title: Git for Windows(1)
urlname: ctpp2m
date: "2021-01-03 15:27:43"
updated: "2021-01-03 15:27:43"
trans: Git_for_Windows_1
cover: "https://img.imql.life/Git_for_Windows.jpg"
categories:
  - Git for Windows
---

来记录一下 Git for Windows 的使用。

<!-- more -->

每次打开 VS Code 时右下角总提示这个，还是更新一下吧，直接点击更新 GIT。
![更新GIT.png](https://img.imql.life/illustrations/fb328d651f90b0b7d5b1ed17a769ad1b.png)
原来是跳转到 Git 官网。
![Git官网.png](https://img.imql.life/illustrations/49642368a8b49a9e27a6140151119c56.png)
这里会跳转到 IE 浏览器，呵呵，赶紧到 Windows 的所有设置-应用-默认应用中把 Web 浏览器设置成 Microsoft Edge 再打开 Git 官网。
![Microsoft-Edge.png](https://img.imql.life/illustrations/ad6888a2fea387856d8baa033dc53ac7.png)
常规操作：下载，双击安装。
![下载安装.png](https://img.imql.life/illustrations/08bb2e08290e40db3eb9e69936fa637a.png)
Only show new option，嗯，很人性化！好评！
![Only-show-new-option.png](https://img.imql.life/illustrations/11235d61743499c09ee4213e948bac64.png)
勾选第二个，以后用`git init`初始化仓库时默认分支名就为 main 了。
{% note info %}
由于某些原因，2020 年 10 月 1 日，GitHub 将启用 main 作为默认分支名，master 将成为历史！
{% endnote %}
![main.png](https://img.imql.life/illustrations/fb85638f9e675246e96c768a2e0508fe.png)
这个直接 Next，默认即可。
![默认.png](https://img.imql.life/illustrations/9889adc45794ac4f9332a62f87c57626.png)
credential helper，凭据帮助器？这是个什么玩意儿？star 一下这个[cross-platform version of the Git Credential Manager](https://github.com/microsoft/Git-Credential-Manager-Core)先，有时间看看（虽然看不懂）。
![credential-helper.png](https://img.imql.life/illustrations/820471caf59fe166a007826c487eca93.png)
实验性的选项：允许在 Git Bash 窗口中运行原生控制台程序，如 Node 或 Python，而不使用 winpty，但它仍然有已知的 bug，不勾选。
![实验性的选项.png](https://img.imql.life/illustrations/a0638f800a6f973846264a1c6c3574b8.png)
安装中：
![安装中.png](https://img.imql.life/illustrations/99ff20fbaedc4a6c0c745f6b75a46b20.png)
完成：
![完成.png](https://img.imql.life/illustrations/9bca4345653a15db144629de460eb41a.png)
Release Notes：
![Release_Notes.png](https://img.imql.life/illustrations/78ac6dacbde953b924dec8b941e39491.png)
