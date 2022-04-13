---

title: Git for Windows(1)

trans: Git_for_Windows(1)

date: 2021-01-03 15:27:43

cover: https://img.imql.life/Git_for_Windows.jpg

categories:

- Git for Windows

---

来记录一下 Git for Windows 的使用。

<!-- more -->

每次打开 VS Code 时右下角总提示这个，还是更新一下吧，直接点击更新 GIT。

![更新GIT.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643951127864-c14322f9-bb21-4d1c-a074-03cd4da0c03b.png#clientId=u906adfca-539a-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8816a99d&name=%E6%9B%B4%E6%96%B0GIT.png&originHeight=138&originWidth=565&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13352&status=done&style=shadow&taskId=u483aaac4-b86d-45d5-8fbc-a285f6ddbfb&title=)

原来是跳转到 Git 官网。

![Git官网.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643951316704-2acb10bc-cf96-4280-9707-949537a5bc3e.png#clientId=u906adfca-539a-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u77e90d8e&name=Git%E5%AE%98%E7%BD%91.png&originHeight=182&originWidth=471&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9766&status=done&style=shadow&taskId=ue7c481bb-2268-4a4b-a694-feba3f55771&title=)

这里会跳转到 IE 浏览器，呵呵，赶紧到 Windows 的所有设置-应用-默认应用中把 Web 浏览器设置成 Microsoft Edge 再打开 Git 官网。

![Microsoft-Edge.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643951379297-05775071-b796-4521-a262-9770c53de1cf.png#clientId=u906adfca-539a-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u88ab399e&name=Microsoft-Edge.png&originHeight=1030&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=508154&status=done&style=shadow&taskId=uaac7f3b1-38aa-4d20-a4f9-3464ee14fba&title=)

常规操作：下载，双击安装。

![下载安装.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643951445357-6a124f54-569e-455d-9cd1-f5d71cebb794.png#clientId=u906adfca-539a-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u4e9bc784&name=%E4%B8%8B%E8%BD%BD%E5%AE%89%E8%A3%85.png&originHeight=1030&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=333164&status=done&style=shadow&taskId=ua4250a31-e1db-43d1-8666-1db21e47cf0&title=)

Only show new option，嗯，很人性化！好评！

![Only-show-new-option.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643951672672-15c2ff00-de6f-4c9a-a4f2-80e2efeead7a.png#clientId=u906adfca-539a-4&crop=0.0017&crop=0&crop=0.9949&crop=0.9958&from=drop&height=475&id=uc894e2d5&name=Only-show-new-option.png&originHeight=478&originWidth=586&originalType=binary&ratio=1&rotation=0&showTitle=false&size=29330&status=done&style=shadow&taskId=uf8558b41-dd54-4740-8607-03a8a7f8212&title=&width=582)

勾选第二个，以后用`git init`初始化仓库时默认分支名就为 main 了。

{% note info %}

由于某些原因，2020 年 10 月 1 日，GitHub 将启用 main 作为默认分支名，master 将成为历史！

{% endnote %}

![main.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643951732653-242c5720-21b2-4f54-abb3-b1c8fcb6fdc5.png#clientId=u906adfca-539a-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u2fd2a225&name=main.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28962&status=done&style=shadow&taskId=u3d01f301-52e9-42bb-9188-1fb64d7f6f6&title=)

这个直接 Next，默认即可。

![默认.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643952196982-c8641abc-bf6e-4912-901c-0160a6f61d8f.png#clientId=u906adfca-539a-4&crop=0.0034&crop=0&crop=0.9966&crop=0.9979&from=drop&height=475&id=u8fe18bd2&margin=%5Bobject%20Object%5D&name=%E9%BB%98%E8%AE%A4.png&originHeight=478&originWidth=586&originalType=binary&ratio=1&rotation=0&showTitle=false&size=27150&status=done&style=shadow&taskId=ub0e29e55-9f8d-4640-9a80-282fd50a8b3&title=&width=582)

credential helper，凭据帮助器？这是个什么玩意儿？star 一下这个[cross-platform version of the Git Credential Manager](https://github.com/microsoft/Git-Credential-Manager-Core)先，有时间看看（虽然看不懂）。

![credential-helper.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643952172008-75dc7581-16b9-43dc-8396-c039c8fb2fae.png#clientId=u906adfca-539a-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uf1e9fbf0&name=credential-helper.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=false&size=27911&status=done&style=shadow&taskId=u2dec92f2-ef40-4c17-9046-bca115f99b7&title=)

实验性的选项：允许在 Git Bash 窗口中运行原生控制台程序，如 Node 或 Python，而不使用 winpty，但它仍然有已知的 bug，不勾选。

![实验性的选项.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643952298581-2e912cbf-b16f-4627-804f-8d4226e000ca.png#clientId=u906adfca-539a-4&crop=0.004&crop=0&crop=0.994&crop=0.9948&from=drop&height=385&id=u8a9dd26f&name=%E5%AE%9E%E9%AA%8C%E6%80%A7%E7%9A%84%E9%80%89%E9%A1%B9.png&originHeight=389&originWidth=503&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25728&status=done&style=shadow&taskId=u9017d1c3-e810-41e9-9f08-8d49bea263d&title=&width=498)

安装中：

![安装中.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643952596757-0d5df1c8-4c35-4ad8-97e3-e1a28063495a.png#clientId=u906adfca-539a-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u106a6bb0&name=%E5%AE%89%E8%A3%85%E4%B8%AD.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=false&size=14854&status=done&style=shadow&taskId=u6054635d-cad8-44ba-b065-66346d9cdc8&title=)

完成：

![完成.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643952623038-8b83b2ce-9541-4a63-b69e-aa6ddbc903d2.png#clientId=u906adfca-539a-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uf5d46387&name=%E5%AE%8C%E6%88%90.png&originHeight=476&originWidth=582&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20170&status=done&style=shadow&taskId=u226c884d-3888-4c1b-b1cb-6399c0c3246&title=)

Release Notes：

![Release_Notes.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643952645402-f24244c2-0669-4d59-b112-79a8dfcab1ca.png#clientId=u906adfca-539a-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ue47eff3e&name=Release_Notes.png&originHeight=745&originWidth=1303&originalType=binary&ratio=1&rotation=0&showTitle=false&size=93429&status=done&style=shadow&taskId=u3db4e7b9-6a68-404c-b946-43d2e43e439&title=)
