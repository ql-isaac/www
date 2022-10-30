---

title: Oracle 数据库从入门到精通（一）

trans: Oracle_Database_Learning_1

date: 2020-02-29 18:22:37

cover: https://img.imql.life/Oracle.jpg

tags:

- Oracle Database 11g Release 2
- Windows 10
- openEuler 22.03 LTS
- VMware® Workstation 15 Pro

categories:

- Oracle 数据库从入门到精通

---

Oracle 数据库，又名 Oracle RDBMS，或简称 Oracle。是[甲骨文公司](https://baike.baidu.com/item/%E7%94%B2%E9%AA%A8%E6%96%87%E5%85%AC%E5%8F%B8/430115)的一款[关系型数据库管理系统](https://baike.baidu.com/item/%E5%85%B3%E7%B3%BB%E6%95%B0%E6%8D%AE%E5%BA%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F/11032386)。它是在数据库领域一直处于领先地位的产品。可以说 Oracle 数据库是目前世界上最流行的关系型数据库管理系统之一，系统可移植性好、使用方便、功能强，适用于各类大、中、小微机环境。它是一种高效率的、可靠性好的、适应高吞吐量的数据库方案。

<!-- more -->

## 下载

访问官方[Oracle Database 11g Release 2 下载地址](https://www.oracle.com/database/technologies/oracle-database-software-downloads.html)下载即可，注意有两个压缩包，下好后分别右键解压到当前目录，这样就得到了安装文件夹 database。

## Windows 中的安装（试验）

1. 打开 database 文件夹，双击 setup.exe 安装，刚开始有一个如下图的错误，解决办法是编辑 database 下的 stage 下的 cvu 下的 cvu_prereq.xml，在 <CERTIFIED_SYSTEMS></CERTIFIED_SYSTEMS> 间的最后位置添加以下代码，保存并关闭，重新安装即可。

![](https://img.imql.life/illustrations/Fu1t9n6CXTPpEmHFOl7DL9S9KvEA.png)

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

![](https://img.imql.life/illustrations/FpIEA0xKgRbMjsvirmLQN-fJETlb.png)

3. 直接下一步；

![](https://img.imql.life/illustrations/Fu3du5SITUHt-XTkxJI3Rl0ZgNA2.png)

4. 选择服务器类，下一步；

![](https://img.imql.life/illustrations/Fu1MwQsvgFEH580vS-h1j_At60iU.png)

5. 直接下一步；

![](https://img.imql.life/illustrations/Fn0igM0hUP0GRx5aYxZqQV1un2Cm.png)

6. 选择高级安装，下一步；

![](https://img.imql.life/illustrations/FpGLESRvADs5pS9S87PWBBMLJue5.png)

7. 默认即可，下一步；

![](https://img.imql.life/illustrations/FqMloHUdpYt8mzmeBEaLnRBHWeMO.png)

8. 就选择企业版，下一步；

![](https://img.imql.life/illustrations/FmTKng4Vm3fc_DtAzwKU6pyWQtCC.png)

9. 默认即可，下一步；

![](https://img.imql.life/illustrations/FjpIApY2jZXIVSVeN3YtQoljCd-q.png)

10. 默认即可，下一步；

![](https://img.imql.life/illustrations/FrHKlc4ZUZoikxaj-L5ovAmbXfi9.png)

11. 自定义 SID 的名称，不改，就默认也行；

![](https://img.imql.life/illustrations/FkcW40Se8z6o6GySX18QNxzUiZgA.png)

12. 使用 Unicode 字符集；

![](https://img.imql.life/illustrations/FmkItSDOC-3Ak-CR3OCB4HMKqzCh.png)

13. 勾选创建具有示例方案的数据库，下一步；

![](https://img.imql.life/illustrations/Fm4EqLiwQnypirXPInFXDXlPLtKE.png)

14. 默认即可，下一步；

![](https://img.imql.life/illustrations/FsygCzt3AiTcQjp4CWi4u6bp6IhH.png)

15. 默认即可，下一步；

![](https://img.imql.life/illustrations/FnB00R1HwJ7GdDiClhIKOLL2DMKR.png)

16. 不启动自动备份，下一步；

![](https://img.imql.life/illustrations/FswvhxU3Cm-uOKYLOi4iuobhgPRO.png)

17. 个人学习用，为了方便，选择对所有账户使用相同的口令（口令必须以字母开头），下一步；

![](https://img.imql.life/illustrations/FjUXWgObtagDBo7P7tvFOqCvanJA.png)

18. 检查到错误，可以忽略，勾选全部忽略，下一步；

![](https://img.imql.life/illustrations/FrSqYq02smyWyXJRTNw5sIYvkKVm.png)

19. 点击完成，等待；

![](https://img.imql.life/illustrations/Fq_dk3-hko6OAXFVwGOgdagmZ1V2.png)

20. 点击口令管理；

![](https://img.imql.life/illustrations/Fjh5EkuB7ixpCJCJd4l_eSZiUp-t.png)

21. 设置 SYS 用户密码为 change_on_install，设置 SYSTEM 用户密码为 manager，解锁 SCOTT 用户并设置密码为 tiger，解锁 SH 用户并设置密码为 sh；

![](https://img.imql.life/illustrations/Fjf4ANQ7RVIy7bT5tUd_WWCRdtS4.png)

22. 安装完成；

![](https://img.imql.life/illustrations/Fmstuc3Oz3gBJNZwZNuWe-DdfJrq.png)

## SQL PLUS 的使用

### 登录 SCOTT 用户

命令行 CMD 里输入 sqlplus，输入 scott，再输入密码 tiger（不会回显），即可登录 SCOTT 用户。

![](https://img.imql.life/illustrations/Fnc3L8Ib4dLiVUH_9wtiy_lgLqpd.gif)

### 第一次查询

数据库最重要的组成对象是表，登录上 SCOTT 用户后，首先通过以下命令查询一下该用户有哪些表吧。

```sql
SELECT * FROM TAB;
```

![](https://img.imql.life/illustrations/Fq5sngqOmHArG1_8t1Or8reBs833.gif)

呃，查询结果显示得比较乱，有一个命令可以解决这个问题，如下，设置每行显示的数据长度，执行完这个命令后再查询一下 SCOTT 用户有哪些表看看。

```
SET LINESIZE 100
```

![](https://img.imql.life/illustrations/Fip4EU4-COueQrV9cSD04n_lxKZm.gif)

呃，如果觉得 TNAME 列的数据所占的长度太长了，有一个命令可以解决这个问题，如下，设置 TNAME 列的数据所占的长度，执行完这个命令后再查询一下 SCOTT 用户有哪些表看看。

```
COL TNAME FOR A20
```

![](https://img.imql.life/illustrations/Fv8PG6hg28bqnlQM8x0TL20C69xJ.gif)

终于，能很舒服地查看到 SCOTT 用户下有四个表：BONUS、DEPT、EMP 和 SALGRADE。那么，再查询一下 DEPT 表吧。

```sql
SELECT * FROM DEPT;
```

![](https://img.imql.life/illustrations/FrJTfDJsdDMVLvIUNtYrB4JjEFG7.gif)

### 切换用户

换个用户登录是怎样的命令？如下命令格式，其中`[]`表示可选内容，`|`表示多选一。

```
CONN[ECT] 用户名/密码 [AS SYSDBA|SYSUSER]
```

登录 SYS 用户看看，由于 SYS 是超级管理员用户，命令如下：

```
CONN SYS/change_on_install AS SYSDBA
```

![](https://img.imql.life/illustrations/FhbPseepP9QCna0NFS6JYiRMWREy.png)

登录 SYSTEM 用户看看，由于 SYSTEM 是普通管理员用户，命令如下：

```
CONN SYSTEM/manager
```

![](https://img.imql.life/illustrations/FkkYNOBw8giLivweeweTy5AXXSQv.png)

SYSTEM 用户和 SYS 用户都是管理员，应该是可以查询到 SCOTT 用户的 DEPT 表的，来试试。

```sql
SELECT * FROM DEPT;
```

![](https://img.imql.life/illustrations/FiuZggslqxoH7QL5sqHjciwGXpV8.png)

来确认一下当前用户是否是管理员用户。

```
SHOW USER
```

![](https://img.imql.life/illustrations/FhrZ4JTh2G9nh2N5SGV6mttDA-fd.png)

这就奇怪了，难道不能查询到？原来，是需要在表前指定用户。

```sql
SELECT * FROM SCOTT.DEPT;
```

![](https://img.imql.life/illustrations/FoPnZRr-G9b52BAxIEQGhnLKdQ2N.png)

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

![](https://img.imql.life/illustrations/FkY4V4cKgM6E8Jrz9uXV_HEAMYQE.png)

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

![](https://img.imql.life/illustrations/FgaZwRQJc3nBeKarhB-avwAEC2ph.png)

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

![](https://img.imql.life/illustrations/FtL7QWjays3MH7yydpJFFCs-_SvL.png)

SALGRADE 的结构解释：

| 字段  | 含义             | 类型   | 类型作用 | 说明 |
| ----- | ---------------- | ------ | -------- | ---- |
| GRADE | 等级编号         | NUMBER |          |      |
| LOSAL | 此等级的最低工资 | NUMBER |          |      |
| HISAL | 此等级的最高工资 | NUMBER |          |      |

### 工资表（BONUS)

BONUS 表没有数据，只有表结构。

![](https://img.imql.life/illustrations/Fpx5EGG257GFJsaScAb4DXbkLe8R.png)

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
