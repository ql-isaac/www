---
title: 什么是 Git？
trans: What_is_Git
date: 2020-01-24 22:53:47
cover: https://image.ql-isaac.cn/Git.gif
tags:
  - Git v2.25.0.windows.1
  - Git v2.17.1
  - Windows 10 专业版
  - Ubuntu 18.04 LTS

categories:
  - [Git 和 GitHub 从入门到实践]
  - [Git for Windows]
  - [Git]
---

Git 是一个目前世界上最流行的开源分布式版本控制系统。

<!-- more -->

## Git 的诞生

Git 是[林纳斯·托瓦兹](https://www.baidu.com/s?wd=%E6%9E%97%E7%BA%B3%E6%96%AF%C2%B7%E6%89%98%E7%93%A6%E5%85%B9&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)为了帮助管理 [Linux](https://baike.baidu.com/item/Linux/27050) 内核开发而开发的。在 2002 年以前，世界各地的志愿者还是以一种传统的方式将源代码文件发给林纳斯·托瓦兹，然后由他本人通过手工方式合并代码。当时虽然有 CSV、SVN 这些免费的版本控制系统，但是速度慢、需要联网，也有一些商用的版本控制系统，虽然比 CSV、SVN 好用，但是不开源，和 Linux 的开源精神不符。2002 年，Linux 系统已经发展了十年，代码库之大让林纳斯·托瓦兹很难继续通过手工方式管理，最终林纳斯·托瓦兹选择了一个商业的版本控制系统 BitKeeper，BitKeeper 的东家 BitMover 公司出于人道主义精神，授权 Linux 社区免费使用这个版本控制系统，这看起来是一个很好的局面。Linux 社区牛人聚集，2005 年，开发 Samba 的 Andrew 试图破解 BitKeeper 的协议的行为被 BitMover 公司发现，Linux 社区的 BitKeeper 免费使用权被收回，于是，[林纳斯·托瓦兹](https://www.baidu.com/s?wd=%E6%9E%97%E7%BA%B3%E6%96%AF%C2%B7%E6%89%98%E7%93%A6%E5%85%B9&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)花了两周时间自己用 C 写了一个分布式版本控制系统，Git 诞生！之后，Git 迅速成为最流行的分布式版本控制系统，随即，2008 年，GitHub 网站上线，它为开源项目免费提供 Git 存储，无数开源项目开始迁移至 GitHub，包括 jQuery、PHP、Ruby 等等。

## 安装和配置 Git

我在《我的 HexoBlog 的诞生（一）》中已经完成了 Git 的安装和配置，不过那只是在 Windows 上，而且也没详细讲，这里就详细讲解一下如何在 Windows 和 Linux 上安装和配置 Git 吧。

### Windows 10 上安装和配置 Git

1. 双击安装程序；

![安装程序.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641178284305-49f1e0cc-866d-4508-9fc0-d3288481f6d8.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=0.9004&crop=1&from=drop&height=197&id=u1d3c8813&name=%E5%AE%89%E8%A3%85%E7%A8%8B%E5%BA%8F.png&originHeight=219&originWidth=281&originalType=binary&ratio=1&rotation=0&showTitle=true&size=8867&status=done&style=shadow&taskId=u7790ca76-4bfa-4010-a4c3-e175398148d&title=%E5%AE%89%E8%A3%85%E7%A8%8B%E5%BA%8F&width=253 "安装程序")

2. GNU 许可证。不看，Next；

![许可协议.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641178427208-4444f7e1-9a88-4609-a274-7ce57390acbf.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8ac4132b&name=%E8%AE%B8%E5%8F%AF%E5%8D%8F%E8%AE%AE.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=17015&status=done&style=shadow&taskId=u6f542c07-6b1a-4ce5-9743-ae210b00724&title=%E8%AE%B8%E5%8F%AF%E5%8D%8F%E8%AE%AE "许可协议")

3. 设置安装路径。可以将 C 改为 D，安装在 D 盘，这里就不改了，Next；

![设置安装路径 .png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641178655003-c0454bf3-639a-429e-aea7-698191e7a201.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ud5834ad3&name=%E8%AE%BE%E7%BD%AE%E5%AE%89%E8%A3%85%E8%B7%AF%E5%BE%84%20.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=12226&status=done&style=shadow&taskId=ub7160dbe-0336-4991-a4b9-70b9dc80e9d&title=%E8%AE%BE%E7%BD%AE%E5%AE%89%E8%A3%85%E8%B7%AF%E5%BE%84 "设置安装路径")

4. 安装组件。第一个选项是说是否创建桌面快捷方式，可以不勾选，下面六个都勾选了，为默认，不更改，倒数第一个是说是否检查更新，可以不勾选，倒数第二个是说是否在所有控制台窗口中使用 TrueType 字体，勾选，Next；

![安装组件.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641178769225-b08d3395-057a-4324-b0d0-91ceda014901.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u9b09e6d5&name=%E5%AE%89%E8%A3%85%E7%BB%84%E4%BB%B6.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=16922&status=done&style=shadow&taskId=ub9c679d6-576e-4717-9956-6ab7a37648e&title=%E5%AE%89%E8%A3%85%E7%BB%84%E4%BB%B6 "安装组件")

5. 开始菜单设置。直接 Next；

![开始菜单设置.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641178833151-f8e2b6e8-4509-4eb1-b8e2-6d781ce1ab0b.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uc9468b98&name=%E5%BC%80%E5%A7%8B%E8%8F%9C%E5%8D%95%E8%AE%BE%E7%BD%AE.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=12401&status=done&style=shadow&taskId=ue8823ae4-d964-4ab8-aa20-83b195cb33d&title=%E5%BC%80%E5%A7%8B%E8%8F%9C%E5%8D%95%E8%AE%BE%E7%BD%AE "开始菜单设置")

6. 设置 Git 的默认文本编辑器：就选择 Vim，Next；

![设置Git的默认文本编辑器.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641178872491-a5b0a117-4e88-4763-96fa-06f8cfc098e7.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u1217b175&name=%E8%AE%BE%E7%BD%AEGit%E7%9A%84%E9%BB%98%E8%AE%A4%E6%96%87%E6%9C%AC%E7%BC%96%E8%BE%91%E5%99%A8.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=16037&status=done&style=shadow&taskId=u1e1b8815-b719-4de4-9542-213e380fe04&title=%E8%AE%BE%E7%BD%AEGit%E7%9A%84%E9%BB%98%E8%AE%A4%E6%96%87%E6%9C%AC%E7%BC%96%E8%BE%91%E5%99%A8 "设置Git的默认文本编辑器")

7. 调整 PATH 环境。就选择默认推荐的，Next，该推荐项是说仅向 PATH 添加一些最小的 Git 包装器，以避免使用可选的 Unix 工具造成环境混乱，能够通过 Git Bash、命令提示符、Windows PowerShell 以及在 PATH 中寻找 Git 的任何第三方软件使用 Git；

![调整Path环境.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641179029053-d4a6c150-df0a-4053-9c9f-57b08e17a6b8.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u169f4091&name=%E8%B0%83%E6%95%B4Path%E7%8E%AF%E5%A2%83.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=20312&status=done&style=shadow&taskId=u456d7356-959e-4aaf-8bb6-43f81a9fbc3&title=%E8%B0%83%E6%95%B4Path%E7%8E%AF%E5%A2%83 "调整Path环境")

8. 选择 HTTPS 后端传输。第一个选项是说使用 OpenSSL 库，服务器证书将使用 ca-bundle.crt 文件进行验证，这是我们常用的选项，第二个选项是说使用本地 Windows 安全通道库，服务器证书将使用 Windows 证书存储验证，此选项还允许使用公司的内部根 CA 证书，例如通过 Active Directory Domain Services，这里，就默认第一个选项，Next；

![选择HTTPS后端传输.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641179075232-c7e7f91c-4def-4a86-a5e7-71a87bef659f.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u26d200f2&name=%E9%80%89%E6%8B%A9HTTPS%E5%90%8E%E7%AB%AF%E4%BC%A0%E8%BE%93.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=14572&status=done&style=shadow&taskId=u2e0e0c23-8b5e-4e70-9047-7d893b5beb8&title=%E9%80%89%E6%8B%A9HTTPS%E5%90%8E%E7%AB%AF%E4%BC%A0%E8%BE%93 "选择HTTPS后端传输")

9. 配置行尾符号转换：第一个选项是说签出 Windows 风格，提交 Unix 风格的行尾，即签出文本文件时，Git 会将 LF 转换为 CRLF，提交文本文件时，CRLF 将转换为 LF，对于跨平台项目，这是 Windows 上的推荐设置（“core.autocrlf”设置为“true”）。第二个选项是说按原样签出，提交 Unix 样式的行尾，签出文本文件时，Git 不会执行任何转换，提交文本文件时，CRLF 将转换为 LF，对于跨平台项目，这是 Unix 上的建议设置（“core.autocrlf”设置为“input”）。第三个选项是说按原样签出，按原样提交，当签出或提交文本文件时，Git 不会执行任何转换，不建议跨平台项目选择此选项（“core.autocrlf”设置为“false”），这里，就默认第一个选项，Next；

![配置行尾符号转换.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641179249173-76d79586-5bee-42ea-80ff-69a9e734e4cc.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ua68a3445&name=%E9%85%8D%E7%BD%AE%E8%A1%8C%E5%B0%BE%E7%AC%A6%E5%8F%B7%E8%BD%AC%E6%8D%A2.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=19377&status=done&style=shadow&taskId=u793ed08e-87d1-493e-bba0-8f94805b636&title=%E9%85%8D%E7%BD%AE%E8%A1%8C%E5%B0%BE%E7%AC%A6%E5%8F%B7%E8%BD%AC%E6%8D%A2 "配置行尾符号转换")

10. 配置终端模拟器以与 Git Bash 一起使用。第一个选项是说使用 MinTTY（MSYS2 的默认终端），Git Bash 将使用 MinTTY 作为终端模拟器，该模拟器具有可调整大小的窗口，非矩形选择和 Unicode 字体，Windows 控制台程序（例如交互式 Python）必须通过“ winpty”启动才能在 MinTTY 中运行，第二个选项是说使用 Windows 的默认控制台窗口，Git 将使用 Windows 的默认控制台窗口（“cmd.exe”），该窗口可以与 Win32 控制台程序（如交互式 Python 或 node.js）一起使用，但默认的回滚非常有限，需要配置为使用 unicode 字体以正确显示非 ASCII 字符，并且在 Windows 10 之前，其窗口不能自由调整大小，并且只允许矩形文本选择，这里，就默认第一个选项，Next；

![配置终端模拟器以与Git_Bash一起使用.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641179399063-2a07170e-5c27-4432-ac5e-a3754cec4521.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u7540b37f&name=%E9%85%8D%E7%BD%AE%E7%BB%88%E7%AB%AF%E6%A8%A1%E6%8B%9F%E5%99%A8%E4%BB%A5%E4%B8%8EGit_Bash%E4%B8%80%E8%B5%B7%E4%BD%BF%E7%94%A8.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=19415&status=done&style=shadow&taskId=ub8ec82ad-345c-4404-ba3c-839be803856&title=%E9%85%8D%E7%BD%AE%E7%BB%88%E7%AB%AF%E6%A8%A1%E6%8B%9F%E5%99%A8%E4%BB%A5%E4%B8%8EGit_Bash%E4%B8%80%E8%B5%B7%E4%BD%BF%E7%94%A8 "配置终端模拟器以与Git_Bash一起使用")

11. 配置额外的选项。第一个选项是说启用文件系统缓存，文件系统数据将被批量读取并缓存在内存中用于某些操作（“core.fscache”设置为“true”）， 这可以显着地提升性能，第二个选项是说启用 Git 凭证管理器，Windows 的 Git 凭证管理器为 Windows 提供安全的 Git 凭证存储，最显著的是对 Visual Studio Team Services 和 GitHub 的多因素身份验证支持（需要 .NET Framework v4.5.1 或更高版本），第三个选项是说启用符号链接，启用符号链接需要 SeCreateSymbolicLink 权限，现有存储库不受此设置的影响，这里，就默认第一个和第二个选项，Install；

![配置额外的选项.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641179651298-8cde55eb-63e1-493d-976d-1018c31e05b8.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u02402a4d&name=%E9%85%8D%E7%BD%AE%E9%A2%9D%E5%A4%96%E7%9A%84%E9%80%89%E9%A1%B9.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=18070&status=done&style=shadow&taskId=u8c159a65-578c-4cb0-bf88-0550238b35c&title=%E9%85%8D%E7%BD%AE%E9%A2%9D%E5%A4%96%E7%9A%84%E9%80%89%E9%A1%B9 "配置额外的选项")

12. 安装完成；

![安装完成.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641179773566-b02c0c22-8877-4ff8-83c3-8939f1fe3ba5.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ucf964047&name=%E5%AE%89%E8%A3%85%E5%AE%8C%E6%88%90.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=true&size=11399&status=done&style=shadow&taskId=u368953d4-33f2-4056-88ba-5bd48ddcd41&title=%E5%AE%89%E8%A3%85%E5%AE%8C%E6%88%90 "安装完成")

13. Release Notes；

![Release_Notes.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641179985585-79bd8bb6-3092-43cf-9211-2e316b2139ed.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u159bd7fa&name=Release_Notes.png&originHeight=745&originWidth=1303&originalType=binary&ratio=1&rotation=0&showTitle=true&size=93429&status=done&style=shadow&taskId=u60241037-11d8-4b45-9322-9b389482f7e&title=Release%20Notes "Release Notes")

14. 至此 Git 就算安装完毕了，之后需要去 [Github](https://github.com/) 注册一个自己的账号，注意需要绑定自己的邮箱，建议是谷歌邮箱；

![注册.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641180069375-cedc2cf5-a4b0-4b0f-bb23-d7b60aad3049.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u624b5810&name=%E6%B3%A8%E5%86%8C.png&originHeight=931&originWidth=1894&originalType=binary&ratio=1&rotation=0&showTitle=true&size=195800&status=done&style=shadow&taskId=u2f2760dc-62c0-4522-9416-58627f08b03&title=%E6%B3%A8%E5%86%8C "注册")

15. 在桌面右键，点击 Git Bash Here；

![桌面右键.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641180133971-478b48d6-6d80-4e87-a832-a5d1af00c1fb.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u483abb1b&name=%E6%A1%8C%E9%9D%A2%E5%8F%B3%E9%94%AE.png&originHeight=456&originWidth=342&originalType=binary&ratio=1&rotation=0&showTitle=true&size=32046&status=done&style=shadow&taskId=u590c272d-6a15-47bb-8472-7f1613f4274&title=%E6%A1%8C%E9%9D%A2%E5%8F%B3%E9%94%AE "桌面右键")

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

![SSH.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641180408889-8f216cad-6f9c-4fc9-96a0-be5e36114818.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u62ec69ac&name=SSH.png&originHeight=742&originWidth=1408&originalType=binary&ratio=1&rotation=0&showTitle=true&size=25985&status=done&style=shadow&taskId=u3ed67174-eeee-4ac6-9920-63e4db30100&title=SSH "SSH")

18. Github 和 Gitee 的 SSH 公钥配置。登录自己的 Github 账号，点击右上角的头像，点击 Setting，点击左侧的 SSH and GPG keys，点击右侧的 New SSH key，填写 Tile（自定义），粘贴刚复制的内容为 Key，最后点击 Add SSH key，关于 Gitee 的方式大同小异；
19. 测试一下。执行`ssh -T git@github.com`或`ssh -T git@gitee.com`，输入 yes 回车，出现以下提示，表示本机和自己的 GitHub/Gitee 账号绑定成功。

```
Hi <自己的Github/Gitee用户名>! You've successfully authenticated, but <GitHub/Gitee> does not provide shell access.
```

### Ubuntu 18.04 LTS 上安装和配置 Git

1. 相比在 Windows 上，在 Linux 上安装和配置 Git 的步骤就比较少了。在终端输入以下命令回车执行，确保系统和 apt 包列表完全更新；

```bash
sudo apt-get update -y
```

![更新.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641181066804-59d7067e-3c68-48ee-964a-0865dc97f1bf.png#clientId=u1deebcc9-da4d-4&crop=0&crop=0.7062&crop=1&crop=1&from=drop&height=497&id=u38b0790b&name=%E6%9B%B4%E6%96%B0.png&originHeight=497&originWidth=735&originalType=binary&ratio=1&rotation=0&showTitle=true&size=85616&status=done&style=shadow&taskId=u5b154b63-128b-487f-8c76-68658e04c3b&title=%E6%9B%B4%E6%96%B0&width=735 "更新")

2. 在终端输入以下命令回车，安装 Git，可再输入下一个命令查看 Git 版本；

```bash
sudo apt install git
```

```bash
git --version
```

![安装Git.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1641181199668-5c02386d-6b89-4923-833d-22c02567bdc7.gif#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u22771912&name=%E5%AE%89%E8%A3%85Git.gif&originHeight=518&originWidth=779&originalType=binary&ratio=1&rotation=0&showTitle=true&size=1455979&status=done&style=shadow&taskId=ua3497739-c94e-4edc-93fc-11cad4fb86d&title=%E5%AE%89%E8%A3%85Git "安装Git")

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

![Git的工作流程.jpg](https://cdn.nlark.com/yuque/0/2022/jpeg/8391941/1641181909520-5175a27f-0d39-415d-a55c-42e04ae3ab61.jpeg#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ud2719d67&name=Git%E7%9A%84%E5%B7%A5%E4%BD%9C%E6%B5%81%E7%A8%8B.jpg&originHeight=1202&originWidth=1037&originalType=binary&ratio=1&rotation=0&showTitle=true&size=82423&status=done&style=shadow&taskId=u778e2a78-b5ee-4a6f-841a-b46f0481862&title=Git%E7%9A%84%E5%B7%A5%E4%BD%9C%E6%B5%81%E7%A8%8B "Git的工作流程")

## Git 工作区、暂存区和版本库

- 工作区：工作目录的实际情况。
- 暂存区：即工作副本（修改）。
- 版本库：即历史提交。

下面这个图展示了工作区、版本库中的暂存区和版本库之间的关系：
![Git工作区、暂存区和版本库.jpg](https://cdn.nlark.com/yuque/0/2022/jpeg/8391941/1641181933724-4d619abd-3237-4f8d-818a-9afdac37279d.jpeg#clientId=u1deebcc9-da4d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uddb5f373&name=Git%E5%B7%A5%E4%BD%9C%E5%8C%BA%E3%80%81%E6%9A%82%E5%AD%98%E5%8C%BA%E5%92%8C%E7%89%88%E6%9C%AC%E5%BA%93.jpg&originHeight=921&originWidth=1133&originalType=binary&ratio=1&rotation=0&showTitle=true&size=93215&status=done&style=shadow&taskId=u23584885-4b74-4503-b5a5-4ea61f398d0&title=Git%E5%B7%A5%E4%BD%9C%E5%8C%BA%E3%80%81%E6%9A%82%E5%AD%98%E5%8C%BA%E5%92%8C%E7%89%88%E6%9C%AC%E5%BA%93 "Git工作区、暂存区和版本库")

1. 当对当前工作区编辑（M）、添加（A）或删除（D）的文件执行 git add 命令时，暂存区的目录树被更新；
2. 当执行提交操作（git commit）时，暂存区转化为版本库的下一次提交；
3. 当执行`git reset HEAD`命令时，暂存区的目录树会被重写，被版本库最新版本（HEAD）替换，但是工作区不受影响；
4. 当执行`git checkout .`或者`git checkout -- <file>`命令时，会用暂存区全部或指定的文件替换工作区的文件。这个操作很危险，会清除工作区中未添加到暂存区的改动；
5. 当执行`git rm --cached <file>`命令时，会直接从暂存区删除文件，工作区则不做出改变；
6. 当执行`git checkout HEAD .`或者`git checkout HEAD <file>`命令时，会用版本库最新版本（HEAD）全部或者部分文件替换暂存区以及工作区中的文件。这个命令也是极具危险性的，因为不但会清除工作区中未添加到暂存区的改动，也会清除暂存区中未提交的改动。
