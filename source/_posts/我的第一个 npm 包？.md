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

![20MB.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641302610139-378fc392-6601-4d23-a662-49a93b7c80f5.png#clientId=u0be106e6-455f-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u1eb29bc8&name=20MB.png&originHeight=93&originWidth=966&originalType=binary&ratio=1&rotation=0&showTitle=true&size=8394&status=done&style=shadow&taskId=ua6ed906e-7a2e-4db1-b5e4-4afc66e7922&title=20MB "20MB")

首先是注册自己的 npm 账号：

![注册.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641302658975-de1073f9-f7f9-45b1-b5e3-f533a819f386.png#clientId=u0be106e6-455f-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ub762cb3f&name=%E6%B3%A8%E5%86%8C.png&originHeight=1030&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=true&size=60079&status=done&style=shadow&taskId=u35b64903-9585-47f5-9ddf-c804aba2d51&title=%E6%B3%A8%E5%86%8C "注册")

然后认证一下刚刚填写的邮箱：

![Continue.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1641302713102-9eff3913-a7ff-49ad-8d91-702e036fa6d6.png#clientId=u0be106e6-455f-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u0a020c1a&name=Continue.png&originHeight=525&originWidth=727&originalType=binary&ratio=1&rotation=0&showTitle=true&size=22018&status=done&style=shadow&taskId=ue2d15842-47ef-4ef3-be31-96aabd46fbb&title=Continue "Continue")

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

![Token.png](https://cdn.nlark.com/yuque/0/2021/png/8391941/1640791330817-fbde3e76-b721-4c9c-af42-49213dacf5b2.png#clientId=ue6c9e26d-2bd2-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ua795709b&name=Token.png&originHeight=660&originWidth=1900&originalType=binary&ratio=1&rotation=0&showTitle=true&size=92313&status=done&style=shadow&taskId=u182127f3-0506-4e4a-9d50-c121b3856ff&title=Token "Token")

接着执行如下命令进行初始化，依次填写信息，回车确认。

```bash
npm init
```

依次填写信息，回车确认：

![init.png](https://cdn.nlark.com/yuque/0/2021/png/8391941/1640792844577-bb08312f-d419-4e83-ad31-a7c58bc384d5.png#clientId=ue6c9e26d-2bd2-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u77ed4f0b&name=init.png&originHeight=824&originWidth=981&originalType=binary&ratio=1&rotation=0&showTitle=true&size=72379&status=done&style=shadow&taskId=uf3e1dd7d-f419-4265-86a5-fc58ba40224&title=%E5%88%9D%E5%A7%8B%E5%8C%96 "初始化")

执行如下命令，“稍稍”等待一会，Gifs 就被发布到 npm 上去了。

```bash
npm publish
```

每次有新的 Gif 需要发布，都需要执行上面的命令进行全量的发布，每次都要比前一次“稍稍”多等待一会，非常难受。这里可以利用 GitHub Actions 自动进行发布，我们只需将新的 Gif 推送到自己的 Gifs 仓库即可。
