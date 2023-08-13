---
title: Oracle 数据库从入门到精通（一）
urlname: kooclp
date: "2020-02-29 18:22:37"
updated: "2023-08-12 11:15:15"
trans: Oracle_Database_Learning_1
cover: "https://img.imql.life/Oracle.jpg"
tags:
  - Oracle Database
  - Windows
  - openEuler
  - VMware Workstation
categories:
  - Oracle 数据库从入门到精通
---

Oracle 数据库，又名 Oracle RDBMS，或简称 Oracle。是[甲骨文公司](https://baike.baidu.com/item/%E7%94%B2%E9%AA%A8%E6%96%87%E5%85%AC%E5%8F%B8/430115)的一款[关系型数据库管理系统](https://baike.baidu.com/item/%E5%85%B3%E7%B3%BB%E6%95%B0%E6%8D%AE%E5%BA%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F/11032386)。它是在数据库领域一直处于领先地位的产品。可以说 Oracle 数据库是目前世界上最流行的关系型数据库管理系统之一，系统可移植性好、使用方便、功能强，适用于各类大、中、小微机环境。它是一种高效率的、可靠性好的、适应高吞吐量的数据库方案。

<!-- more -->

## 下载

访问官方[Oracle Database 11g Release 2 下载地址](https://www.oracle.com/database/technologies/oracle-database-software-downloads.html)下载即可，注意有两个压缩包，下好后分别右键解压到当前目录，这样就得到了安装文件夹 database。

## Windows 中的安装（试验）

1. 打开 database 文件夹，双击 setup.exe 安装，刚开始有一个如下图的错误，解决办法是编辑 database 下的 stage 下的 cvu 下的 cvu_prereq.xml，在 <CERTIFIED_SYSTEMS></CERTIFIED_SYSTEMS> 间的最后位置添加以下代码，保存并关闭，重新安装即可。

![错误.png](https://img.imql.life/illustrations/9cbcbb0ab24cfeedc4b7d32bfc081831.png)

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

![不更新.png](https://img.imql.life/illustrations/d6b6503cc911bf779b12b11719b12c3c.png)

3. 直接下一步；

![创建.png](https://img.imql.life/illustrations/f936ba2a2bc3f42c21a57ae2ac23fc48.png)

4. 选择服务器类，下一步；

![服务器类.png](https://img.imql.life/illustrations/28ec4b944c432fdc60e75a76a4865d43.png)

5. 直接下一步；

![单实例.png](https://img.imql.life/illustrations/87d9077b6eaaae1bed20505c4303b1da.png)

6. 选择高级安装，下一步；

![高级安装.png](https://img.imql.life/illustrations/7adddb02e30eec83574055d9d2f180b7.png)

7. 默认即可，下一步；

![语言.png](https://img.imql.life/illustrations/23feb2079402e442f37ce4d318fe2856.png)

8. 就选择企业版，下一步；

![企业版.png](https://img.imql.life/illustrations/591002452978b5655e39c274030db687.png)

9. 默认即可，下一步；

![默认即可.png](https://img.imql.life/illustrations/c85f848a19cacab7ec849bb72985ef36.png)

10. 默认即可，下一步；

![下一步.png](https://img.imql.life/illustrations/847db7b0444b8f81ff9707e28b75fb44.png)

11. 自定义 SID 的名称，不改，就默认也行；

![自定义SID的名称.png](https://img.imql.life/illustrations/4b1d62220097d1bb830920d7482fdb3c.png)

12. 使用 Unicode 字符集；

![Unicode.png](https://img.imql.life/illustrations/56e4a294745a787a266c6eb3ed295beb.png)

13. 勾选创建具有示例方案的数据库，下一步；

![创建具有示例方案的数据库.png](https://img.imql.life/illustrations/4329a29ade7d592ce3f5137b55ba3fb5.png)

14. 默认即可，下一步；

![过.png](https://img.imql.life/illustrations/dbb8e5bc935e3780245f9c2878f8ece7.png)

15. 默认即可，下一步；

![再过.png](https://img.imql.life/illustrations/de14134acaa3ab65aa1cee353ae393f3.png)

16. 不启动自动备份，下一步；

![不自动备份.png](https://img.imql.life/illustrations/33013940fc50f3e69fb8c754253512be.png)

17. 个人学习用，为了方便，选择对所有账户使用相同的口令（口令必须以字母开头），下一步；

![设置口令.png](https://img.imql.life/illustrations/699b540900965bb168f0b0ac50d26e1c.png)

18. 检查到错误，可以忽略，勾选全部忽略，下一步；

![检查到错误.png](https://img.imql.life/illustrations/86ad81fe84257e4d2c991fb94673af7f.png)

19. 点击完成，等待；

![等待.png](https://img.imql.life/illustrations/e340fe1278d73b0d6499bd94755d29d4.png)

20. 点击口令管理；

![口令管理.png](https://img.imql.life/illustrations/eef8a835cd7c67259f844e24e97f5485.png)

21. 设置 SYS 用户密码为 change_on_install，设置 SYSTEM 用户密码为 manager，解锁 SCOTT 用户并设置密码为 tiger，解锁 SH 用户并设置密码为 sh；

![是.png](https://img.imql.life/illustrations/a15ee76a72779bec7fbfdc002a7a2e16.png)

22. 安装完成；

![完成.png](https://img.imql.life/illustrations/8e10647a76d84bb23da8848e1b4b2494.png)

## SQL PLUS 的使用

### 登录 SCOTT 用户

命令行 CMD 里输入 sqlplus，输入 scott，再输入密码 tiger（不会回显），即可登录 SCOTT 用户。
![登录scott用户.gif](https://img.imql.life/illustrations/4d54a3a8888faa6127189fe4ae76b8d9.gif)

### 第一次查询

数据库最重要的组成对象是表，登录上 SCOTT 用户后，首先通过以下命令查询一下该用户有哪些表吧。

```sql
SELECT * FROM TAB;
```

![第一次查询.gif](https://img.imql.life/illustrations/36d5ea105c5d84ba1c09fc4fb162902a.gif)
呃，查询结果显示得比较乱，有一个命令可以解决这个问题，如下，设置每行显示的数据长度，执行完这个命令后再查询一下 SCOTT 用户有哪些表看看。

```
SET LINESIZE 100
```

![显示问题.gif](https://img.imql.life/illustrations/8b704d98d4a5fe2aad78efc79cc3f91b.gif)
呃，如果觉得 TNAME 列的数据所占的长度太长了，有一个命令可以解决这个问题，如下，设置 TNAME 列的数据所占的长度，执行完这个命令后再查询一下 SCOTT 用户有哪些表看看。

```
COL TNAME FOR A20
```

![太长了.gif](https://img.imql.life/illustrations/44c29b688c3275865e98d0a52d7845df.gif)
终于，能很舒服地查看到 SCOTT 用户下有四个表：BONUS、DEPT、EMP 和 SALGRADE。那么，再查询一下 DEPT 表吧。

```sql
SELECT * FROM DEPT;
```

![再查询一下DEPT表.gif](https://img.imql.life/illustrations/1c7320f709ef054651820500f050fe0e.gif)

### 切换用户

换个用户登录是怎样的命令？如下命令格式，其中`[]`表示可选内容，`|`表示多选一。

```
CONN[ECT] 用户名/密码 [AS SYSDBA|SYSUSER]
```

登录 SYS 用户看看，由于 SYS 是超级管理员用户，命令如下：

```
CONN SYS/change_on_install AS SYSDBA
```

![切换到sys用户.png](https://img.imql.life/illustrations/e55c8364facc5b7fe8dda63121f2f9c6.png)
登录 SYSTEM 用户看看，由于 SYSTEM 是普通管理员用户，命令如下：

```
CONN SYSTEM/manager
```

![切换到system用户.png](https://img.imql.life/illustrations/ec9dee24372800541c77fbaa824c635f.png)
SYSTEM 用户和 SYS 用户都是管理员，应该是可以查询到 SCOTT 用户的 DEPT 表的，来试试。

```sql
SELECT * FROM DEPT;
```

![表或视图不存在.png](https://img.imql.life/illustrations/78d43e0fa461a3da43e95cccdcb8afbf.png)
来确认一下当前用户是否是管理员用户。

```
SHOW USER
```

![SHOWUSER.png](https://img.imql.life/illustrations/4891eca420ce091258299c8f4aa60bf9.png)
这就奇怪了，难道不能查询到？原来，是需要在表前指定用户。

```sql
SELECT * FROM SCOTT.DEPT;
```

![加用户名.png](https://img.imql.life/illustrations/8123b6bd896f8c7d24a33dadacbb6563.png)

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

![DEPT的结构.png](https://img.imql.life/illustrations/db27a795564e07a020bdcbb016eed049.png)
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
![EMP.png](https://img.imql.life/illustrations/fe0de0c3ab6e8ec2b0b94357641e112c.png)
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

![SALGRADE.png](https://img.imql.life/illustrations/d966bd263885c62ce5bbaf8911d60ef2.png)
SALGRADE 的结构解释：

| 字段  | 含义             | 类型   | 类型作用 | 说明 |
| ----- | ---------------- | ------ | -------- | ---- |
| GRADE | 等级编号         | NUMBER |          |      |
| LOSAL | 此等级的最低工资 | NUMBER |          |      |
| HISAL | 此等级的最高工资 | NUMBER |          |      |

### 工资表（BONUS)

BONUS 表没有数据，只有表结构。
![BONUS.png](https://img.imql.life/illustrations/38c59b2a4f3f4be5ae359c04163b580b.png)
BONUS 的结构解释：

| 字段  | 含义     | 类型         | 类型作用       | 说明 |
| ----- | -------- | ------------ | -------------- | ---- |
| ENAME | 雇员姓名 | VARCHAR2(10) | 最多 10 位字符 |      |
| JOB   | 职位     | VARCHAR2(9)  | 最多 9 位字符  |      |
| SAL   | 基本工资 | NUMBER       |                |      |
| COMM  | 佣金     | NUMBER       |                |      |

## Linux 中的安装（正式）

### 软硬件检查

1. 查看操作系统版本；

```bash
cat /etc/openEuler-release
```

```
openEuler release 22.03 LTS
```

2. 查看内存；

```bash
free -m
```

```
               total        used        free      shared  buff/cache   available
Mem:            3380         244        2641          17         494        2768
Swap:           4023           0        4023
```

3. 查看共享内存；

## 参考

- [【李兴华带你玩编程】Oracle 数据库小白教程（bilibili）](https://www.bilibili.com/video/BV1NJ411M7fE?p=80)
