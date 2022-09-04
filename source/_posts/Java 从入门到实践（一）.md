---
title: Java 从入门到实践（一）
trans: Java_Learning_1
date: 2020-02-06 16:03:27
cover: https://img.imql.life/Java.jpg
tags:
  - JDK 9.0.4
  - Windows 10
  - VMware® Workstation 15 Pro

categories:
  - Java 从入门到实践
---

Java——面向对象编程语言的领军者！

<!-- more -->

## 搭建 Java 学习环境

### 安装 VMware pro 15

下载[学习版](https://www.52pojie.cn/thread-1026907-1-1.html)，安装步骤不多说了，只是有一点建议，也是我装软件的原则：能不装 C 盘就别装 C 盘。

### 安装 Windows 10

我在网上找到一个[精简版的 Windows 10 系统](https://www.cnblogs.com/gxhunter/p/10290748.html)，有介绍和下载方式，这回就用这个精简版的镜像。由于是安装 Windows 系统，具体如何安装这里就不再多说了。

### 安装 JDK 9.0.4

[下载 JDK 9.0.4](https://pan.baidu.com/s/1R0Y6nDqlYxKvelV3dAtekQ)，提取码：ua1e，下好后安装，安装路径可以自定义，公共 JRE 可装可不装，如下图，我这次装一装。
![安装.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643950683233-758724b8-9150-4a02-8430-cd48330015a7.png#clientId=u5ff9c625-7df9-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u5cbeb679&name=%E5%AE%89%E8%A3%85.png&originHeight=476&originWidth=625&originalType=binary&ratio=1&rotation=0&showTitle=false&size=42805&status=done&style=shadow&taskId=u033ecad2-8edd-48a9-a420-b9188bbaa81&title=)

### 配置系统环境变量

右键此电脑->属性->高级系统设置->高级->环境变量，点击下方的新建，变量名填写 JAVA_HOME，变量值就是安装 JDK 9.0.4 时设置的路径，确定。
如下图，在系统变量栏中找到 Path 变量，点击编辑，点击新建，键入 %JAVA_HOME%\bin，确定。运行 CMD，键入 java，发现系统识别了 java 命令。
![Path.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643950697495-8251c080-cd53-438b-9621-e4c5849c77f4.png#clientId=u5ff9c625-7df9-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u45eb6e35&name=Path.png&originHeight=777&originWidth=794&originalType=binary&ratio=1&rotation=0&showTitle=false&size=29929&status=done&style=shadow&taskId=ubd0b9da3-4da1-43cb-af7b-92e50129abe&title=)

## String（字符串）

## 类集框架

## 参考

- [黑马 Java 零基础入门到就业\_Java 基础（IDEA 版本）](https://www.bilibili.com/video/BV1Lf4y1U7Cz?p=9)
