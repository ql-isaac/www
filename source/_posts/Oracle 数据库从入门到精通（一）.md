---

title: Oracle 数据库从入门到精通（一）

trans: Oracle_Database_Learning_1

date: 2020-02-29 18:22:37

cover: https://img.imql.life/Oracle.jpg

tags:

- Oracle Database 11g Release 2
- Windows 10
- VMware® Workstation 15 Pro

categories:

- Oracle 数据库从入门到精通

---

Oracle 数据库，又名 Oracle RDBMS，或简称 Oracle。是[甲骨文公司](https://baike.baidu.com/item/%E7%94%B2%E9%AA%A8%E6%96%87%E5%85%AC%E5%8F%B8/430115)的一款[关系型数据库管理系统](https://baike.baidu.com/item/%E5%85%B3%E7%B3%BB%E6%95%B0%E6%8D%AE%E5%BA%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F/11032386)。它是在数据库领域一直处于领先地位的产品。可以说 Oracle 数据库是目前世界上最流行的关系型数据库管理系统之一，系统可移植性好、使用方便、功能强，适用于各类大、中、小微机环境。它是一种高效率的、可靠性好的、适应高吞吐量的数据库方案。

<!-- more -->

## 下载 Oracle Database 11g Release 2

访问官方[Oracle Database 11g Release 2 下载地址](https://www.oracle.com/database/technologies/oracle-database-software-downloads.html)下载即可，注意有两个压缩包，下好后分别右键解压到当前目录，这样就得到了安装文件夹 database。

## 安装和配置 Oracle Database 11g Release 2

1. 打开 database 文件夹，双击 setup.exe 安装，刚开始有一个如下图的错误，解决办法是编辑 database 下的 stage 下的 cvu 下的 cvu_prereq.xml，在 <CERTIFIED_SYSTEMS></CERTIFIED_SYSTEMS> 间的最后位置添加以下代码，保存并关闭，重新安装即可。

![错误.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887174629-08bfc059-1f94-4514-a2a0-8c85a4268583.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u58f2b866&name=%E9%94%99%E8%AF%AF.png&originHeight=164&originWidth=512&originalType=binary&ratio=1&rotation=0&showTitle=false&size=6505&status=done&style=shadow&taskId=ufb38e3a4-b5e9-4bb5-bc37-f18a675aacb&title=)

```xml
<OPERATING_SYSTEM RELEASE="6.2">
        <VERSION VALUE="3"/>
        <ARCHITECTURE VALUE="64-bit"/>
        <NAME VALUE="Windows 10"/>
        <ENV_VAR_LIST>
            <ENV_VAR NAME="PATH" MAX_LENGTH="1023" />
        </ENV_VAR_LIST>
</OPERATING_SYSTEM>
```

2. 不更新，下一步；

![不更新.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887201950-1799df57-b860-4602-b76f-0a8877965251.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ue153df75&name=%E4%B8%8D%E6%9B%B4%E6%96%B0.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=84990&status=done&style=shadow&taskId=ucaefe411-5acf-4435-b388-34b31315c1e&title=)

3. 直接下一步；

![创建.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887292954-60e21422-4eac-4dc7-b160-f6e5680d54bd.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u12f31353&name=%E5%88%9B%E5%BB%BA.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=77920&status=done&style=shadow&taskId=u8223edcf-5fc3-4d30-9eb6-c56bb257f71&title=)

4. 选择服务器类，下一步；

![服务器类.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887314922-49796f04-3112-4a8b-b5e7-cc91ed08c224.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u7a8af2f6&name=%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%B1%BB.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=83386&status=done&style=shadow&taskId=ue569abe6-7ddb-4668-a616-3eca511044c&title=)

5. 直接下一步；

![单实例.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887364828-49d50504-5fae-470c-9942-8ff338a9ca40.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u28b5c3ca&name=%E5%8D%95%E5%AE%9E%E4%BE%8B.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=78634&status=done&style=shadow&taskId=ue990203a-0ce9-43c2-ab8c-4f66e4ea6fd&title=)

6. 选择高级安装，下一步；

![高级安装.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887398900-288ae843-3303-4b2d-b69f-ac18d5de5f55.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8f8402e8&name=%E9%AB%98%E7%BA%A7%E5%AE%89%E8%A3%85.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=87867&status=done&style=shadow&taskId=u5939accb-29e6-497f-8ff3-0bc2502f486&title=)

7. 默认即可，下一步；

![语言.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887419943-ed5be26f-cae6-4cd4-8a3f-694387cc9f70.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ue8fb83f3&name=%E8%AF%AD%E8%A8%80.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=101911&status=done&style=shadow&taskId=ufd45838b-34d7-474a-addb-8a13caf0d97&title=)

8. 就选择企业版，下一步；

![企业版.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887599335-87121fc3-283e-453c-9be4-e205b43bb761.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u60d903b2&name=%E4%BC%81%E4%B8%9A%E7%89%88.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=120618&status=done&style=shadow&taskId=u04b70144-e0ee-4fc3-aa47-903e65e6a72&title=)

9. 默认即可，下一步；

![默认即可.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887622278-a592333e-feb2-47f5-8b83-f9e9695decde.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u5835c009&name=%E9%BB%98%E8%AE%A4%E5%8D%B3%E5%8F%AF.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=94744&status=done&style=shadow&taskId=u304e32f5-5dc4-4c22-862c-ec39da3cddc&title=)

10. 默认即可，下一步；

![下一步.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887666708-799de7e8-fe20-4b60-8fd6-ee086fe2da5c.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u0788bca8&name=%E4%B8%8B%E4%B8%80%E6%AD%A5.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=97629&status=done&style=shadow&taskId=uc4b77139-e36a-4eb8-b2ed-3ca40fd9209&title=)

11. 自定义 SID 的名称，不改，就默认也行；

![自定义SID的名称.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887680111-d74d0be3-6d2b-4a8c-b42f-51d0d522eb32.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u3c319dce&name=%E8%87%AA%E5%AE%9A%E4%B9%89SID%E7%9A%84%E5%90%8D%E7%A7%B0.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=102318&status=done&style=shadow&taskId=uc5b8c58e-6b17-48d4-82f8-dda5c097786&title=)

12. 使用 Unicode 字符集；

![Unicode.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887715743-df8cd029-9d94-4771-9eb8-cffa7df44834.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u1052594e&name=Unicode.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=111561&status=done&style=shadow&taskId=ub4061a74-5248-408e-9c23-162b4d2f9fb&title=)

13. 勾选创建具有示例方案的数据库，下一步；

![创建具有示例方案的数据库.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887734914-5680fee4-7078-48c4-be85-f95b265dceab.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u048cc28f&name=%E5%88%9B%E5%BB%BA%E5%85%B7%E6%9C%89%E7%A4%BA%E4%BE%8B%E6%96%B9%E6%A1%88%E7%9A%84%E6%95%B0%E6%8D%AE%E5%BA%93.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=102197&status=done&style=shadow&taskId=u31acb424-b566-46e2-8e11-2ebc5873215&title=)

14. 默认即可，下一步；

![过.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887805625-b881da70-3e2c-4729-bad6-45432e026000.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u9318d89a&name=%E8%BF%87.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=114534&status=done&style=shadow&taskId=u9bda54ea-eb54-45e2-949c-39c33e30157&title=)

15. 默认即可，下一步；

![再过.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887834693-a38186d0-bebc-4375-b0e9-e57319c86156.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ube7bb011&name=%E5%86%8D%E8%BF%87.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=119499&status=done&style=shadow&taskId=u65903251-0d30-4dfd-8b47-528e7f14f9b&title=)

16. 不启动自动备份，下一步；

![不自动备份.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887852617-72c97a5f-36fe-4e86-b110-6e8e702e3d81.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u91999204&name=%E4%B8%8D%E8%87%AA%E5%8A%A8%E5%A4%87%E4%BB%BD.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=104666&status=done&style=shadow&taskId=u2695f53e-d490-4377-903d-9eff77525e0&title=)

17. 个人学习用，为了方便，选择对所有账户使用相同的口令（口令必须以字母开头），下一步；

![设置口令.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887927175-55bc1813-c663-4ffb-83b6-8c4f473cc6ab.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=uc62b415f&name=%E8%AE%BE%E7%BD%AE%E5%8F%A3%E4%BB%A4.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=110973&status=done&style=shadow&taskId=u4cf30191-ae3f-4972-a5ae-69d83af1a64&title=)

18. 检查到错误，可以忽略，勾选全部忽略，下一步；

![检查到错误.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887960801-1ecacbc8-7805-4b03-8dcc-74d93955e823.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u049d257e&name=%E6%A3%80%E6%9F%A5%E5%88%B0%E9%94%99%E8%AF%AF.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=130710&status=done&style=shadow&taskId=u992a1691-947b-4765-805b-c06ef3abed7&title=)

19. 点击完成，等待；

![等待.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887976992-aa3627a6-2b66-42bd-a180-63edc3246be1.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u865460c7&name=%E7%AD%89%E5%BE%85.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=140595&status=done&style=shadow&taskId=u7654a1b7-4c3d-4a9c-87fa-5624eb5a08f&title=)

20. 点击口令管理；

![口令管理.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643887996731-80bad73b-acff-46a3-a654-b08e18c0c1e2.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u638ee5f7&name=%E5%8F%A3%E4%BB%A4%E7%AE%A1%E7%90%86.png&originHeight=541&originWidth=453&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13302&status=done&style=shadow&taskId=uf704a2f5-3164-4221-a51b-77c3ebaf282&title=)

21. 设置 SYS 用户密码为 change_on_install，设置 SYSTEM 用户密码为 manager，解锁 SCOTT 用户并设置密码为 tiger，解锁 SH 用户并设置密码为 sh；

![是.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888221739-cf994199-b170-40e6-b01f-ef3f33fb7376.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ufd86f5dd&name=%E6%98%AF.png&originHeight=302&originWidth=423&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5053&status=done&style=shadow&taskId=u6579e01b-4f19-4ddd-a636-6e4cd80e076&title=)

22. 安装完成；

![完成.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888239720-2a5c1fda-2871-42be-a216-3f067d589050.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u5512cbc3&name=%E5%AE%8C%E6%88%90.png&originHeight=741&originWidth=982&originalType=binary&ratio=1&rotation=0&showTitle=false&size=92548&status=done&style=shadow&taskId=ubba47c61-3763-4ffa-ae1c-2a9398de571&title=)

## SQL PLUS 的使用

### 登录 SCOTT 用户

命令行 CMD 里输入 sqlplus，输入 scott，再输入密码 tiger（不会回显），即可登录 SCOTT 用户。

![登录scott用户.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1643888283466-28d19682-e83d-43fd-89b3-330f1ddbf6d9.gif#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u5e608f47&name=%E7%99%BB%E5%BD%95scott%E7%94%A8%E6%88%B7.gif&originHeight=852&originWidth=1249&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2926996&status=done&style=shadow&taskId=ubafb4db8-6440-45d0-9985-7b37484bbc4&title=)

### 第一次查询

数据库最重要的组成对象是表，登录上 SCOTT 用户后，首先通过以下命令查询一下该用户有哪些表吧。

```sql
SELECT * FROM TAB;
```

![第一次查询.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1643888297842-b4098bb6-8005-4567-b3a5-ad98f712b313.gif#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u50be0838&name=%E7%AC%AC%E4%B8%80%E6%AC%A1%E6%9F%A5%E8%AF%A2.gif&originHeight=852&originWidth=1249&originalType=binary&ratio=1&rotation=0&showTitle=false&size=295942&status=done&style=shadow&taskId=ufdc2d3c3-c81e-4edb-a896-208450f629b&title=)

呃，查询结果显示得比较乱，有一个命令可以解决这个问题，如下，设置每行显示的数据长度，执行完这个命令后再查询一下 SCOTT 用户有哪些表看看。

```
SET LINESIZE 100
```

![显示问题.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1643888437316-f5092f99-758d-4cae-b3ab-69cab2bf6fb0.gif#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8aa6555a&name=%E6%98%BE%E7%A4%BA%E9%97%AE%E9%A2%98.gif&originHeight=577&originWidth=998&originalType=binary&ratio=1&rotation=0&showTitle=false&size=44579&status=done&style=shadow&taskId=u8da12e2d-707b-41e9-af90-099629de02f&title=)

呃，如果觉得 TNAME 列的数据所占的长度太长了，有一个命令可以解决这个问题，如下，设置 TNAME 列的数据所占的长度，执行完这个命令后再查询一下 SCOTT 用户有哪些表看看。

```
COL TNAME FOR A20
```

![太长了.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1643888494916-caa9316a-6037-4498-b758-be9b742d92de.gif#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u657ab5c3&margin=%5Bobject%20Object%5D&name=%E5%A4%AA%E9%95%BF%E4%BA%86.gif&originHeight=577&originWidth=998&originalType=binary&ratio=1&rotation=0&showTitle=false&size=45958&status=done&style=none&taskId=u2046950d-452b-4ab8-aeeb-fe1edb5c271&title=)

终于，能很舒服地查看到 SCOTT 用户下有四个表：BONUS、DEPT、EMP 和 SALGRADE。那么，再查询一下 DEPT 表吧。

```sql
SELECT * FROM DEPT;
```

![再查询一下DEPT表.gif](https://cdn.nlark.com/yuque/0/2022/gif/8391941/1643888541591-ed09a9be-e220-483e-b186-3a1ed4e48047.gif#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u941f49c7&margin=%5Bobject%20Object%5D&name=%E5%86%8D%E6%9F%A5%E8%AF%A2%E4%B8%80%E4%B8%8BDEPT%E8%A1%A8.gif&originHeight=577&originWidth=998&originalType=binary&ratio=1&rotation=0&showTitle=false&size=54942&status=done&style=none&taskId=u0b4fa041-d25c-4ddf-9d99-761995e7674&title=)

### 切换用户

换个用户登录是怎样的命令？如下命令格式，其中`[]`表示可选内容，`|`表示多选一。

```
CONN[ECT] 用户名/密码 [AS SYSDBA|SYSUSER]
```

登录 SYS 用户看看，由于 SYS 是超级管理员用户，命令如下：

```
CONN SYS/change_on_install AS SYSDBA
```

![切换到sys用户.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888576497-d100b60f-dc59-489b-998a-5be5ce7b3c31.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u6c8a6d4f&name=%E5%88%87%E6%8D%A2%E5%88%B0sys%E7%94%A8%E6%88%B7.png&originHeight=575&originWidth=981&originalType=binary&ratio=1&rotation=0&showTitle=false&size=19962&status=done&style=shadow&taskId=u99fc5eb6-9eb0-4cfb-be7b-c89ed94c86b&title=)

登录 SYSTEM 用户看看，由于 SYSTEM 是普通管理员用户，命令如下：

```
CONN SYSTEM/manager
```

![切换到system用户.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888597679-4dfdac6d-eca0-46f4-a813-62af9e92cd9e.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8d25b7d5&name=%E5%88%87%E6%8D%A2%E5%88%B0system%E7%94%A8%E6%88%B7.png&originHeight=582&originWidth=984&originalType=binary&ratio=1&rotation=0&showTitle=false&size=27043&status=done&style=shadow&taskId=u62b11619-d357-4d73-9605-3ffae391879&title=)

SYSTEM 用户和 SYS 用户都是管理员，应该是可以查询到 SCOTT 用户的 DEPT 表的，来试试。

```sql
SELECT * FROM DEPT;
```

![表或视图不存在.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888625987-1d5fa56f-4ce8-4ebc-a597-b4bbd7bd2f4a.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u81175eea&name=%E8%A1%A8%E6%88%96%E8%A7%86%E5%9B%BE%E4%B8%8D%E5%AD%98%E5%9C%A8.png&originHeight=579&originWidth=983&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25495&status=done&style=shadow&taskId=ufadaf49d-f17f-4ec3-9727-f5369ab64f2&title=)

来确认一下当前用户是否是管理员用户。

```
SHOW USER
```

![SHOWUSER.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888666730-68d49f40-b4ad-4e93-a7e2-d061baf711ac.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ub7b103da&name=SHOWUSER.png&originHeight=578&originWidth=987&originalType=binary&ratio=1&rotation=0&showTitle=false&size=29048&status=done&style=shadow&taskId=uab673fda-fd0b-443d-b0c8-ebda6622afd&title=)

这就奇怪了，难道不能查询到？原来，是需要在表前指定用户。

```sql
SELECT * FROM SCOTT.DEPT;
```

![加用户名.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888716847-e6a2292e-8d5e-431f-99fc-2b7310768752.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u500b18e2&name=%E5%8A%A0%E7%94%A8%E6%88%B7%E5%90%8D.png&originHeight=580&originWidth=984&originalType=binary&ratio=1&rotation=0&showTitle=false&size=27734&status=done&style=shadow&taskId=ue39062d0-0873-4607-bb46-40bdec562db&title=)

## SQL

关系型数据库的理论诞生之后，世界上出现了许多的关系型数据库管理系统，熟悉了 A 关系型数据库管理系统后几乎还得重新学 B 关系型数据库管理系统，这很大程度上是由于每个关系型数据库管理系统都实现了自己的一套语言，语言只是一种工具，弄那么多套语言毫无意义，于是，SQL（Structured Query Language，即结构化查询语言）作为一个标准和一个功能强大的关系型数据库语言诞生了。

SQL 分为以下几类：

- DML（Data Manipulation Language，数据操作语言）：数据查询（SELECT)、数据更新（UPDATE、INSERT 和 DELETE）和事务管理等。
- DDL（Data Definition Language，数据定义语言）：数据对象定义等（用户和数据表等）。
- DCL（Data Control Language，数据控制语言）：授权等。

## SCOTT 的数据表分析

在 Oracle 11g 以前 SCOTT 和其数据表等是会默认给用户提供的，如果在以上安装 Oracle 11g 的步骤 13 中未勾选创建具有示例方案的数据库，我们就需要手动执行一个脚本，该脚本在如下路径。

```
C:\app\ql\product\11.2.0\dbhome_1\RDBMS\ADMIN\scott.sql
```

### 部门信息表（DEPT)

先切换回 SCOTT 用户：

```
CONN SCOTT/tiger
```

查询 DEPT

```sql
SELECT * FROM DEPT;
```

查看数据表的结构的语法：

```
DESC 数据表;
```

查看 DEPT 的结构：

```
DESC DEPT;
```

![DEPT的结构.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888737960-461ab639-5a6b-4bee-8fd6-4794f1fdb3e6.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u7a8f70da&name=DEPT%E7%9A%84%E7%BB%93%E6%9E%84.png&originHeight=684&originWidth=1086&originalType=binary&ratio=1&rotation=0&showTitle=false&size=26301&status=done&style=shadow&taskId=uf89c34b2-b467-4741-86cf-24ef01d2da8&title=)

DEPT 的结构解释：

| 字段   | 含义     | 类型         | 类型作用       | 说明             |
| ------ | -------- | ------------ | -------------- | ---------------- |
| DEPTNO | 部门编号 | NUMBER(2)    | 最多 2 位数字  |                  |
| DNAME  | 部门名称 | VARCHAR2(14) | 最多 14 位字符 | 3 位字符保存中文 |
| LOC    | 部门位置 | VARCHAR2(13) | 最多 13 为字符 |                  |

### 雇员信息表（EMP）

查询 EMP：

```sql
SELECT * FROM EMP;
```

同样有显示问题，设置一行的长度为 150：

```
SET LINESIZE 150
```

再查询 EMP：

![EMP.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888756342-9a5d6340-1baa-413d-a43f-a032f7b11d0a.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u8cdb188c&name=EMP.png&originHeight=687&originWidth=1105&originalType=binary&ratio=1&rotation=0&showTitle=false&size=42876&status=done&style=shadow&taskId=ud1b0817b-9d05-4f0e-a2fc-b42ad5d0b89&title=)

查看 EMP 的结构：

```sql
DESC EMP;
```

EMP 的结构解释：

| 字段     | 含义     | 类型         | 类型作用                         | 说明                             |
| -------- | -------- | ------------ | -------------------------------- | -------------------------------- |
| EMPNO    | 雇员编号 | NUMBER(4)    | 最多 4 位数字                    |                                  |
| ENAME    | 雇员姓名 | VARCHAR2(10) | 最多 10 位字符                   |                                  |
| JOB      | 雇员职位 | VARCHAR2(9)  | 最多 9 位字符                    |                                  |
| MGR      | 领导编号 | NUMBER(4)    | 最多 4 位数字                    | 领导本身也是雇员                 |
| HIREDATE | 雇佣日期 | DATE         |                                  | 包含日期和时间                   |
| SAL      | 基本工资 | NUMBER(7,2)  | 小数位最多 2 位，整数位最多 5 位 |                                  |
| COMM     | 佣金     | NUMBER(7,2)  | 小数位最多 2 位，整数位最多 5 位 | 只有销售职位的雇员才会存在有佣金 |
| DEPTNO   | 部门编号 | NUMBER(2)    | 最多 2 位数字                    | 雇员所在的部门编号               |

### 工资等级表（SALGRADE）

查询 SALGRADE：

```sql
SELECT * FROM SALGRADE;
```

查看 SALGRADE 的结构：

```sql
DESC SALGRADE;
```

![SALGRADE.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888795747-53c55acd-cd80-4e3b-9662-ddb5b64447c0.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=ufbc1b39e&name=SALGRADE.png&originHeight=686&originWidth=1136&originalType=binary&ratio=1&rotation=0&showTitle=false&size=26710&status=done&style=shadow&taskId=u59542dba-02ed-4e49-8c1b-fafb1412d4e&title=)

SALGRADE 的结构解释：

| 字段  | 含义             | 类型   | 类型作用 | 说明 |
| ----- | ---------------- | ------ | -------- | ---- |
| GRADE | 等级编号         | NUMBER |          |      |
| LOSAL | 此等级的最低工资 | NUMBER |          |      |
| HISAL | 此等级的最高工资 | NUMBER |          |      |

### 工资表（BONUS)

BONUS 表没有数据，只有表结构。

![BONUS.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643888853218-aeb5f0b3-b5ee-4022-bf13-943ea07ec8e8.png#clientId=u5e97955b-c739-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u37cefe78&name=BONUS.png&originHeight=684&originWidth=1135&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23015&status=done&style=shadow&taskId=u74f31a60-d0cb-4a67-911c-dc7b9f6730b&title=)

BONUS 的结构解释：

| 字段  | 含义     | 类型         | 类型作用       | 说明 |
| ----- | -------- | ------------ | -------------- | ---- |
| ENAME | 雇员姓名 | VARCHAR2(10) | 最多 10 位字符 |      |
| JOB   | 职位     | VARCHAR2(9)  | 最多 9 位字符  |      |
| SAL   | 基本工资 | NUMBER       |                |      |
| COMM  | 佣金     | NUMBER       |                |      |

## 参考

- [【李兴华带你玩编程】Oracle 数据库小白教程（bilibili）](https://www.bilibili.com/video/BV1NJ411M7fE?p=80)
