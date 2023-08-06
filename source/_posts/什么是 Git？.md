---
title: 什么是 Git？
urlname: itfc94
author: ql-isaac
date: "2020-01-24 22:30:00"
updated: "2023-07-02 12:32:31"
trans: What_is_Git
cover: "https://img.imql.life/Git.gif"
tags:
  - Git
  - Windows
  - Ubuntu
categories:
  - Git 和 GitHub 从入门到实践
---

Git 是一个目前世界上最流行的开源分布式版本控制系统。

<!-- more -->

## Git 的诞生

Git 是[林纳斯·托瓦兹](https://www.baidu.com/s?wd=%E6%9E%97%E7%BA%B3%E6%96%AF%C2%B7%E6%89%98%E7%93%A6%E5%85%B9&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)为了帮助管理 [Linux](https://baike.baidu.com/item/Linux/27050) 内核开发而开发的。在 2002 年以前，世界各地的志愿者还是以一种传统的方式将源代码文件发给林纳斯·托瓦兹，然后由他本人通过手工方式合并代码。当时虽然有 CSV、SVN 这些免费的版本控制系统，但是速度慢、需要联网，也有一些商用的版本控制系统，虽然比 CSV、SVN 好用，但是不开源，和 Linux 的开源精神不符。2002 年，Linux 系统已经发展了十年，代码库之大让林纳斯·托瓦兹很难继续通过手工方式管理，最终林纳斯·托瓦兹选择了一个商业的版本控制系统 BitKeeper，BitKeeper 的东家 BitMover 公司出于人道主义精神，授权 Linux 社区免费使用这个版本控制系统，这看起来是一个很好的局面。Linux 社区牛人聚集，2005 年，开发 Samba 的 Andrew 试图破解 BitKeeper 的协议的行为被 BitMover 公司发现，Linux 社区的 BitKeeper 免费使用权被收回，于是，[林纳斯·托瓦兹](https://www.baidu.com/s?wd=%E6%9E%97%E7%BA%B3%E6%96%AF%C2%B7%E6%89%98%E7%93%A6%E5%85%B9&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)花了两周时间自己用 C 写了一个分布式版本控制系统，Git 诞生！之后，Git 迅速成为最流行的分布式版本控制系统，随即，2008 年，GitHub 网站上线，它为开源项目免费提供 Git 存储，无数开源项目开始迁移至 GitHub，包括 jQuery、PHP、Ruby 等等。

## 安装和配置 Git

我在《我的 HexoBlog 的诞生（一）》中已经完成了 Git 的安装和配置，不过那只是在 Windows 上，而且也没详细讲，这里就详细讲解一下如何在 Windows 和 Linux 上安装和配置 Git 吧。

### Windows 10 上安装和配置 Git

1. 双击安装程序；

![安装程序](https://img.imql.life/illustrations/FqdbaJcI7U--BiKwREBuPLOpYqbG.png "安装程序")

2. GNU 许可证。不看，Next；

![许可协议](https://img.imql.life/illustrations/FrK-DZTrfHStXsAz3GcHscx8tvvu.png "许可协议")

3. 设置安装路径。可以将 C 改为 D，安装在 D 盘，这里就不改了，Next；

![设置安装路径](https://img.imql.life/illustrations/FiRq8BiE-RPTt9MO9LvOSUlIjlV5.png "设置安装路径")

4. 安装组件。第一个选项是说是否创建桌面快捷方式，可以不勾选，下面六个都勾选了，为默认，不更改，倒数第一个是说是否检查更新，可以不勾选，倒数第二个是说是否在所有控制台窗口中使用 TrueType 字体，勾选，Next；

![安装组件](https://img.imql.life/illustrations/FmedYtIBledCkM2u5ZQXal1n51pG.png "安装组件")

5. 开始菜单设置。直接 Next；

![开始菜单设置](https://img.imql.life/illustrations/FvJC-nT_tZGFFiJ_19g2EbFVdkLD.png "开始菜单设置")

6. 设置 Git 的默认文本编辑器：就选择 Vim，Next；

![设置Git的默认文本编辑器](https://img.imql.life/illustrations/FiMhktEGVTfUzGAiblxwasv0AMNM.png "设置Git的默认文本编辑器")

7. 调整 PATH 环境。就选择默认推荐的，Next，该推荐项是说仅向 PATH 添加一些最小的 Git 包装器，以避免使用可选的 Unix 工具造成环境混乱，能够通过 Git Bash、命令提示符、Windows PowerShell 以及在 PATH 中寻找 Git 的任何第三方软件使用 Git；

![调整Path环境](https://img.imql.life/illustrations/FjlUrwUZXYLx0c0WPTIpkVTyZ-Pn.png "调整Path环境")

8. 选择 HTTPS 后端传输。第一个选项是说使用 OpenSSL 库，服务器证书将使用 ca-bundle.crt 文件进行验证，这是我们常用的选项，第二个选项是说使用本地 Windows 安全通道库，服务器证书将使用 Windows 证书存储验证，此选项还允许使用公司的内部根 CA 证书，例如通过 Active Directory Domain Services，这里，就默认第一个选项，Next；

![选择HTTPS后端传输](https://img.imql.life/illustrations/FgfTclCBBASDa_aGj69sNMnG-FYm.png "选择HTTPS后端传输")

9. 配置行尾符号转换：第一个选项是说签出 Windows 风格，提交 Unix 风格的行尾，即签出文本文件时，Git 会将 LF 转换为 CRLF，提交文本文件时，CRLF 将转换为 LF，对于跨平台项目，这是 Windows 上的推荐设置（“core.autocrlf”设置为“true”）。第二个选项是说按原样签出，提交 Unix 样式的行尾，签出文本文件时，Git 不会执行任何转换，提交文本文件时，CRLF 将转换为 LF，对于跨平台项目，这是 Unix 上的建议设置（“core.autocrlf”设置为“input”）。第三个选项是说按原样签出，按原样提交，当签出或提交文本文件时，Git 不会执行任何转换，不建议跨平台项目选择此选项（“core.autocrlf”设置为“false”），这里，就默认第一个选项，Next；

![配置行尾符号转换](https://img.imql.life/illustrations/FtyyIhdzEzBz7no7Z9ZcMujtD60l.png "配置行尾符号转换")

10. 配置终端模拟器以与 Git Bash 一起使用。第一个选项是说使用 MinTTY（MSYS2 的默认终端），Git Bash 将使用 MinTTY 作为终端模拟器，该模拟器具有可调整大小的窗口，非矩形选择和 Unicode 字体，Windows 控制台程序（例如交互式 Python）必须通过“ winpty”启动才能在 MinTTY 中运行，第二个选项是说使用 Windows 的默认控制台窗口，Git 将使用 Windows 的默认控制台窗口（“cmd.exe”），该窗口可以与 Win32 控制台程序（如交互式 Python 或 node.js）一起使用，但默认的回滚非常有限，需要配置为使用 unicode 字体以正确显示非 ASCII 字符，并且在 Windows 10 之前，其窗口不能自由调整大小，并且只允许矩形文本选择，这里，就默认第一个选项，Next；

![配置终端模拟器以与Git_Bash一起使用](https://img.imql.life/illustrations/FtD2J2Pk69hC7FkPlpIw0IXLMpX_.png "配置终端模拟器以与Git_Bash一起使用")

11. 配置额外的选项。第一个选项是说启用文件系统缓存，文件系统数据将被批量读取并缓存在内存中用于某些操作（“core.fscache”设置为“true”）， 这可以显着地提升性能，第二个选项是说启用 Git 凭证管理器，Windows 的 Git 凭证管理器为 Windows 提供安全的 Git 凭证存储，最显著的是对 Visual Studio Team Services 和 GitHub 的多因素身份验证支持（需要 .NET Framework v4.5.1 或更高版本），第三个选项是说启用符号链接，启用符号链接需要 SeCreateSymbolicLink 权限，现有存储库不受此设置的影响，这里，就默认第一个和第二个选项，Install；

![配置额外的选项](https://img.imql.life/illustrations/FjlF9cBVRWBO-ePBycsmsJ3aaf4G.png "配置额外的选项")

12. 安装完成；

![安装完成](https://img.imql.life/illustrations/FuoSX6hl9_gCFpxxAtqc4ykppgTy.png "安装完成")

13. Release Notes；

![Release Notes](https://img.imql.life/illustrations/Fjz6IdAWqm0vio87duHXKCJchXLH.png "Release Notes")

14. 至此 Git 就算安装完毕了，之后需要去 [Github](https://github.com/) 和 [Gitee](https://gitee.com/) 注册一个自己的账号，需要绑定自己的邮箱，Github 的话强烈建议绑定谷歌邮箱；

![注册](https://img.imql.life/illustrations/FoLfpjHW5ebdNy28n7rOUy5qx3Ew.png "注册")

15. 在桌面右键，点击 Git Bash Here；

![桌面右键](https://img.imql.life/illustrations/Fqu0Rbz1qATGm9FzTQjMInV9sPYu.png "桌面右键")

16. 全局用户信息配置。分别输入以下两个命令回车执行，无提示表示命令执行成功，可以用`git config --list`来查看配置好的信息；

```bash
git config --global user.name "<自己的Github用户名>"
```

```bash
git config --global user.email "<自己的Github邮箱>"
```

17. 生成 SSH 秘钥并复制公钥。输入以下命令回车执行，然后连敲三次回车键，此时打开 .ssh 文件夹，其位于自己的 Windows 用户文件夹下，如下图，用文本编辑器打开 id_rsa.pub，Ctrl+A，复制里面全部的内容；

```bash
ssh-keygen -t rsa
```

![SSH](https://img.imql.life/illustrations/Frdi2BIte7tPXk74sLNOHP2IWjB6.png "SSH")

18. Github 和 Gitee 的 SSH 公钥配置。登录自己的 Github 账号，点击右上角的头像，点击 Setting，点击左侧的 SSH and GPG keys，点击右侧的 New SSH key，填写 Tile（自定义），粘贴刚复制的内容为 Key，最后点击 Add SSH key，Gitee 的方式大同小异；
19. 测试一下。执行`ssh -T git@github.com`或`ssh -T git@gitee.com`，输入 yes 回车，出现以下提示，表示本机和自己的 GitHub/Gitee 账号绑定成功。

```
Hi <自己的Github/Gitee用户名>! You've successfully authenticated, but <GitHub/Gitee> does not provide shell access.
```

### Ubuntu 18.04 LTS 上安装和配置 Git

1. 相比在 Windows 上，在 Linux 上安装和配置 Git 的步骤就比较少了。在终端输入以下命令回车执行，确保系统和 apt 包列表完全更新；

```bash
sudo apt-get update -y
```

![更新](https://img.imql.life/illustrations/Fsg0pLxvXhnwDfKP7xVmpIvj_aOK.png "更新")

2. 在终端输入以下命令回车，安装 Git，可再输入下一个命令查看 Git 版本；

```bash
sudo apt install git
```

```bash
git --version
```

![安装Git](https://img.imql.life/illustrations/FiqAP6BEIhiEWdK0CDR8hUn1n2tj.gif "安装Git")

3. 全局用户信息配置。分别输入以下两个命令回车执行，无提示表示命令执行成功，可以用`git config --list`来查看配置好的信息；

```bash
git config --global user.name "<自己的Github用户名>"
```

```bash
git config --global user.email "<自己的Github邮箱>"
```

4. 生成 SSH 秘钥。输入以下命令回车执行，然后连敲三次回车键；

```bash
ssh-keygen -t rsa
```

5. 输入以下命令回车，输入用户密码安装 Vim 文本编辑器；

```bash
sudo apt-get install vim
```

6. 执行以下命令，用 Vim 打开公钥文件，复制其中的内容（不要复制多了，也不要复制少了）；

```bash
vim /home/<自己的用户名>/.ssh/id_rsa.pub
```

7. Github 和 Gitee 的 SSH 公钥配置。登录自己的 Github 账号，点击右上角的头像，点击 Setting，点击左侧的 SSH and GPG keys，点击右侧的 New SSH key，填写 Tile（自定义），粘贴刚复制的内容为 Key，最后点击 Add SSH key，关于 Gitee 的方式大同小异；
8. 测试一下。执行`ssh -T git@github.com`或`ssh -T git@gitee.com`，输入 yes 回车，出现以下提示，表示本机和自己的 GitHub/Gitee 账号绑定成功。

```
Hi <自己的Github/Gitee用户名>! You've successfully authenticated, but <GitHub/Gitee> does not provide shell access.
```

## Git 的工作流程

1. 克隆 Git 资源作为工作副本；
2. 在工作副本中编辑、添加或修改文件；
3. 如果其他人提交了修改，你可以选择更新工作副本；
4. 在提交前查看修改；
5. 提交修改；
6. 在修改完成后，如果发现错误，可以撤回提交并再次修改并提交。

![Git的工作流程](https://img.imql.life/illustrations/FsakOwGQR9T3huqpfajLYvcsMKB5.jpeg "Git的工作流程")

## Git 工作区、暂存区和版本库

- 工作区：工作目录的实际情况。
- 暂存区：即工作副本（修改）。
- 版本库：即历史提交。

下面这个图展示了工作区、版本库中的暂存区和版本库之间的关系：
![Git 工作区、暂存区和版本库.jpg](https://img.imql.life/illustrations/Fp1_zEPfSn95_OWbh7nyvepr6Aq0.jpeg)

1. 当对当前工作区编辑（M）、添加（A）或删除（D）的文件执行 git add 命令时，暂存区的目录树被更新；
2. 当执行提交操作（git commit）时，暂存区转化为版本库的下一次提交；
3. 当执行`git reset`命令时，暂存区被还原为版本库最新版本（HEAD），工作区不受影响；
4. 当执行`git checkout .`或者`git checkout -- <file>`命令时，会用暂存区全部或指定的文件替换工作区的文件。这个操作很危险，会清除工作区中未添加到暂存区的改动；
5. 当执行`git rm --cached <file>`命令时，会直接从暂存区删除文件，工作区则不做出改变；
6. 当执行`git checkout HEAD`或者`git checkout HEAD <file>`命令时，会用版本库最新版本（HEAD）全部或指定的文件替换暂存区以及工作区中的文件。这个命令也是极具危险性的，因为不但会清除工作区中未添加到暂存区的改动，也会清除暂存区中未提交的改动。
