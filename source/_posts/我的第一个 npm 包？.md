---
title: 我的第一个 npm 包？
urlname: mpwxca
author: ql-isaac
date: "2021-09-15 19:00:00"
updated: "2021-09-15 19:00:00"
trans: My_First_Npm_Package
cover: "https://img.imql.life/npm.jpg"
categories:
  - NPM
---

npm，即 Node Package Manager，是随同 NodeJS 一起安装的包管理工具，本质是一个软件注册表。

<!-- more -->

不可告人的缘由，如下图，听说 jsdelivr 对 npm 上的文件限度会大一些，于是决定将我博文的 Gifs 发布到 npm 上，这就成为了我的第一个 npm 包。
![20MB.png](https://img.imql.life/illustrations/FktDEIxKF1-RsaLt7pPsadQZwXYb.png)
注册自己的 npm 账号：
![注册.png](https://img.imql.life/illustrations/FhTqEOZzHdxN8TCF9WdYhi5OnRS-.png)
认证一下刚刚填写的邮箱：
![Continue.png](https://img.imql.life/illustrations/Foju1zTfcX_ctR2st0B76T3BTNZI.png)
进入终端，SSH 方式克隆自己的 Gifs 远程仓库到本地：

```bash
git clone git@github.com.bak:isaac-ql/post-gifs-1.git
```

{% note info %}
以上命令中@后面的域名为博主自己设置的别名，具体情况可见 [Git for Windows(2)](https://www.imql.life/2021/08/22/Git_for_Windows_2/)。
{% endnote %}
执行以下命令添加 npm 用户，需要输入自己刚刚注册好的 npm 用户名、密码和邮箱。

```bash
npm adduser --registry https://registry.npmjs.org
```

```
Username: ql-isaac
Password: <密码>
Email: (this IS public) qinlei.isaac@gmail.com
Logged in as ql-isaac on https://registry.npmjs.org/.
```

此时如果你前往自己的账户，可注意到自动生成了一个 Token：
![Token.png](https://img.imql.life/illustrations/Ft7kZ88uz0_rWaLWiQmzBg-QfN2v.png)
{% note info %}
此 Token 的值记录在用户文件夹下的 .npmrc 中。
{% endnote %}
接着执行如下命令进行初始化。

```bash
npm init
```

依次填写信息，回车确认：
![初始化](https://img.imql.life/illustrations/Fp1TaKWQvXQX4B3hp9L4DrWzHcx0.png "初始化")
执行如下命令，“稍稍”等待一会，Gifs 就被发布到 npm 上去了。

```bash
npm publish --registry https://registry.npmjs.org
```

每次有新的 Gif 需要发布，都需要执行以上命令进行全量的发布，非常难受。这里可以利用 GitHub Actions 自动进行发布，我们只需将新的 Gif 推送到自己的 Gifs 远程仓库即可。
前往 npm 账户下，到达 Tokens 页面，选择 Generate New Token，输入密码，填写 Name 为 GitHub Actions，选择 Type 为 Automation，生成，如下图，复制生成的 Token，最好是先记到密码本中，以便发布其他的 npm 包时复用。
![image.png](https://img.imql.life/illustrations/FlgQGjh2DvsERmyN2M3hVxRM5N1o.png)
前往 Gifs 远程仓库，点击 Settings，点击 Secrets，再点击 New repository secret，填写 Name 为 NPM_TOKEN，右键粘贴以上 Token 为 Secret，点击 Add secret。
新建 GitHub Actions 文件：

```bash
vim .github/workflows/autopublish.yml
```

```yaml
name: autopublish
on:
  push:
    branches:
      - main

jobs:
  post-gifs-1:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: "12.14.0"
          registry-url: https://registry.npmjs.org/
      - run: npm publish
        env:
          NODE_AUTH_TOKEN: ${{secrets.NPM_TOKEN}}
```

添加新的 Gif 后执行以下命令提交到本地仓库。

```bash
git add .
git commit -m "xxxx"
```

增加 npm 包版本号（最后一位版本号加一）：

```bash
npm version patch
```

推送到远程仓库：

```bash
git push
```

不多时，便可看到 GitHub Actions 执行成功，前往 npm 账户下 Packages 页面，可看到我的第一个 npm 包的版本号变为 1.0.1。
