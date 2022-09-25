---

title: 我的第一个 npm 包？

trans: My_First_Npm_Package

date: 2021-09-15 19:00:00

cover: https://img.imql.life/npm.jpg

categories:

- NPM

---

npm，即 Node Package Manager，是随同 NodeJS 一起安装的包管理工具，本质是一个软件注册表。

<!-- more -->

不可告人的缘由，如下图，听说 jsdelivr 对 npm 上的文件限度会大一些，于是决定将我博文的 Gifs 发布到 npm 上，这就成为了我的第一个 npm 包，哈哈。

![](https://img.imql.life/illustrations/FktDEIxKF1-RsaLt7pPsadQZwXYb.png)

首先是注册自己的 npm 账号：

![](https://img.imql.life/illustrations/FhTqEOZzHdxN8TCF9WdYhi5OnRS-.png)

然后认证一下刚刚填写的邮箱：

![](https://img.imql.life/illustrations/Foju1zTfcX_ctR2st0B76T3BTNZI.png)

克隆自己的 Gifs 仓库到本地，进入终端，执行以下命令添加 npm 用户，需要输入自己刚刚注册好的 npm 用户名、密码和邮箱。

```bash
npm adduser
```

```
Username: ql-isaac
Password: <密码>
Email: (this IS public) qinlei.isaac@gmail.com
Logged in as ql-isaac on https://registry.npmjs.org/.
```

此时如果你前往自己的账户，可注意到自动生成了一个 Token：

![](https://img.imql.life/illustrations/Ft7kZ88uz0_rWaLWiQmzBg-QfN2v.png)

接着执行如下命令进行初始化，依次填写信息，回车确认。

```bash
npm init
```

依次填写信息，回车确认：

![](https://img.imql.life/illustrations/Fp1TaKWQvXQX4B3hp9L4DrWzHcx0.png)

执行如下命令，“稍稍”等待一会，Gifs 就被发布到 npm 上去了。

```bash
npm publish
```

每次有新的 Gif 需要发布，都需要执行上面的命令进行全量的发布，每次都要比前一次“稍稍”多等待一会，非常难受。这里可以利用 GitHub Actions 自动进行发布，我们只需将新的 Gif 推送到自己的 Gifs 仓库即可。
