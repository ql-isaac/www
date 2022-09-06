---

title: Git for Windows(2)

trans: Git_for_Windows_2

date: 2021-08-22 16:14:00

cover: https://img.imql.life/Git_for_Windows.jpg

categories:

- Git for Windows

---

来记录一下 Git for Windows 的使用。

<!-- more -->

不可告人的缘由，我需要另外创建一个 GitHub 小号（[isaac-ql](https://github.com/isaac-ql)），创建完账号后，就应该是去绑定个人电脑的 SSH key，我想当然的以为可以复用建博客时生成的 SSH key，结果 GitHub 给我了这个提示：

![Key_is_already_in_use.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643954136162-3f546f39-eadb-45da-8312-c96fa4e4a509.png#clientId=ucdf28f59-c05f-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u6ac7f5a8&name=Key_is_already_in_use.png&originHeight=94&originWidth=259&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3608&status=done&style=shadow&taskId=u264029e6-14a9-452c-a34d-48144d1750e&title=)

好吧，看来是不能复用。百度一番后，解决办法如下：

1. 右键，点击 Git Bash Here，执行以下命令，生成另外一对公钥与私钥，不能与之前的重名：

```bash
ssh-keygen -t rsa -f ~/.ssh/<自定义 SSH key 文件名>
```

2. 将公钥添加到自己的小号里，不多说了；
3. 进入 .ssh 文件夹（在用户文件夹下），新建 config 文件（注意这是 config 是完整文件名），编辑：

```diff
+Host github.com
+    HostName github.com
+    PreferredAuthentications publickey
+    IdentityFile ~/.ssh/id_rsa
+Host <自定义别名>
+    HostName github.com
+    PreferredAuthentications publickey
+    IdentityFile ~/.ssh/<自定义 SSH key 文件名>
```

3. 以后在以 SSH 方式克隆 GitHub 小号时，将原来的地址@后面的域名改为以上的自定义别名即可。

---

如下图，`git clone`很慢怎么办？

![克隆很慢.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643954162586-7784f6a2-f810-43cf-8fa2-7de11123b10f.png#clientId=ucdf28f59-c05f-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ueaa10aa3&name=%E5%85%8B%E9%9A%86%E5%BE%88%E6%85%A2.png&originHeight=77&originWidth=493&originalType=binary&ratio=1&rotation=0&showTitle=false&size=6896&status=done&style=shadow&taskId=ud281fb43-2fee-488d-8b2e-ec2f0efaeab&title=)

请那啥之后设置代理（我使用的代理软件是 Clash）：

1. 要那啥，此处省略一百个字；
2. 右键，点击 Git Bash Here，依次执行以下命令；

```bash
export https_proxy=http://127.0.0.1:<代理端口>
```

{% note info %}

以上命令是设置环境变量，只在当前终端中有效，也可以执行以下命令修改配置以一直生效：

```bash
git config --global https.proxy http://127.0.0.1:<代理端口>
```

{% endnote %}

3. 打开 Clash 的全局代理；
4. 起飞，还没开始截图就克隆完毕了。

![起飞.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643954185940-6531a255-1c0a-4980-888c-e29cbfe270a3.png#clientId=ucdf28f59-c05f-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u9c891679&name=%E8%B5%B7%E9%A3%9E.png&originHeight=104&originWidth=515&originalType=binary&ratio=1&rotation=0&showTitle=false&size=8435&status=done&style=shadow&taskId=uee988a6e-17ab-4594-926b-c5251770829&title=)
