---

title: Python 从入门到实践（二）

trans: Python-Learning(2)

date: 2020-02-10 15:01:37

cover: https://img.imql.life/Python.png

tags:

- Pycharm
- Python v3.8.1
- Windows 10

categories:

- Python 从入门到实践

---

《Python 从入门到实践（一）》是 Python 初级部分的学习笔记，主要是一些基础方面的内容，本篇就为 Python 高级部分的学习笔记，主要是一些面向对象方面的内容。

<!-- more -->

## 搭建实践环境

[下载最流行的最新版的 Python 开发软件 PyCharm](https://www.jetbrains.com/pycharm/download/)，建议下载专业版，但是是收费的，如果你和我一样是用来学习的，可以在网上寻找方法免费使用。

1. 下载好后安装：Next；

![双击运行程序.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643884592107-5ccc0c56-fa21-4092-882e-8cd21ebe0a45.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ufe22dec2&name=%E5%8F%8C%E5%87%BB%E8%BF%90%E8%A1%8C%E7%A8%8B%E5%BA%8F.png&originHeight=477&originWidth=581&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28480&status=done&style=shadow&taskId=uecf2a94c-173d-4de7-9fe2-839103ce01e&title=)

2. 设置安装路径：将 C 改为 D，Next；

![设置安装路径.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643884628655-eb54d14e-3637-4672-83b4-6c47e04f3aa6.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8c50f020&name=%E8%AE%BE%E7%BD%AE%E5%AE%89%E8%A3%85%E8%B7%AF%E5%BE%84.png&originHeight=477&originWidth=581&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13645&status=done&style=shadow&taskId=uf7f50ec5-3a2c-4882-9b85-aa8ed5f34a1&title=)

3. 勾选如图这两个选项，Next；

![勾选.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643884693717-524402cf-8031-4044-92e0-f52f55c60551.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8a08c3be&name=%E5%8B%BE%E9%80%89.png&originHeight=477&originWidth=581&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16663&status=done&style=shadow&taskId=uddb769e3-968b-448e-877a-a4c2a153420&title=)

4. Install;

![Install.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643884745038-0094566a-a5f1-4b05-b708-c206b9f41c91.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u9128baf7&name=Install.png&originHeight=477&originWidth=581&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20499&status=done&style=shadow&taskId=u34c62cff-e084-4705-b666-e33417a68ff&title=)

5. 勾选，Finish；

![Finish.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643884773598-7cbac2ca-0bc7-4ad3-a812-6a155464bbb3.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ua494c16c&name=Finish.png&originHeight=477&originWidth=581&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23296&status=done&style=shadow&taskId=u943be1b7-c372-4bc2-a5b1-5f0fa3b170e&title=)

6. 不导入设定，直接点 OK;

![OK.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643885007893-d2d823d7-86f4-4596-9ef5-9b1dfef462f2.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uea60b9a6&name=OK.png&originHeight=189&originWidth=459&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5853&status=done&style=shadow&taskId=u14c465ea-5407-41d3-9896-51f68de5203&title=)

7. 勾选上，Continue；

![同意.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643885078514-22539e7e-5151-446b-a961-55414f084e1b.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u5415d7b8&name=%E5%90%8C%E6%84%8F.png&originHeight=623&originWidth=681&originalType=binary&ratio=1&rotation=0&showTitle=false&size=48861&status=done&style=shadow&taskId=u117f078e-2ea9-42f5-8dbc-ab99e64412e&title=)

8. Don't sent；

![否.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643885111512-3b216739-ba5c-44c1-a388-0cbb29c536e9.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u56cdfbec&margin=%5Bobject%20Object%5D&name=%E5%90%A6.png&originHeight=354&originWidth=740&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28334&status=done&style=shadow&taskId=u6d6ab706-4b19-4ccf-a770-c95dfd1fc53&title=)

9. 设置 UI 主题；

![Light.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643885211344-a8cfd069-3f81-423a-b743-2556ae868846.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uab49e25d&name=Light.png&originHeight=846&originWidth=1008&originalType=binary&ratio=1&rotation=0&showTitle=false&size=144235&status=done&style=shadow&taskId=u3178cf8a-4a59-46f9-8c13-018d1f0620d&title=)

10. 需要“学习化”，如何“学习化”这里就不多说了；

![激活.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643885316996-ca1298ae-9ebc-4837-8f6b-e5718a2ae82f.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ueee0d200&name=%E6%BF%80%E6%B4%BB.png&originHeight=592&originWidth=890&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18923&status=done&style=shadow&taskId=ua88d360e-68d7-4cff-af36-93f78bfcc3a&title=)

11. 学习化完成后就是创建项目了，点击 Create New Project；

![创建.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643885414351-f9109208-8eaa-4562-ae02-9f6c94ce28ab.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u6297417e&name=%E5%88%9B%E5%BB%BA.png&originHeight=610&originWidth=972&originalType=binary&ratio=1&rotation=0&showTitle=false&size=30224&status=done&style=shadow&taskId=udc220f5a-9e35-4235-840f-cc806a4ddcc&title=)

12. 点击 Browse，找到自定义的文件夹，确定；

![Create.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643885507326-9ed2ff6a-c56f-43f7-8b5d-5add2073135a.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u75c78baf&name=Create.png&originHeight=610&originWidth=833&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20355&status=done&style=shadow&taskId=ucfd88ffe-f557-4476-bcc9-a77484b2325&title=)

13. 进行一些设置，点击 files，点击 Settings，在搜索框中搜索 font，按自己喜好设置字体和字体属性，我这里就仅仅将字体尺寸设大点吧，设为 20，确定；

![font.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643885531948-b78b93c7-863a-4351-b37f-466d819e7fa4.png#clientId=udbd27d95-534e-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8afcf876&name=font.png&originHeight=878&originWidth=1224&originalType=binary&ratio=1&rotation=0&showTitle=false&size=42271&status=done&style=shadow&taskId=uda1be91f-0b9e-40ff-8d2f-72a4353857a&title=)
