---

title: C 从入门到精通（一）

trans: C_Learning_1

date: 2020-02-13 19:56:24

cover: https://img.imql.life/C.jpg

tags:

- Ubuntu 18.04 LTS
- VMware® Workstation 15 Pro

categories:

- C 从入门到精通

---

任何比 C 语言更低级的语言，都不足以完整地抽象一个计算机系统，任何比 C 语言高级的语言，都可以用 C 语言实现。C 语言不像是被发明的，它更像是被发现的，它无可替代、精妙绝伦。

<!-- more -->

## C 语言的简单历史

C 语言是从 B 语言发展而来，B 语言是从 BCPL 发展而来，BCPL 是从 FORTRAN 发展而来。C 语言于 1972 年 11 月问世，1973 年 3 月，第三版的 Unix 上出现了 C 语言的编译器，1973 年 11 月，第四版的 Unix 发布了，这个版本是完全用 C 语言重新写的，1978 年美国电话电报公司（AT&T）贝尔实验室正式发布 C 语言，1983 年美国国家标准局（American National Standards Institute，简称 ANSI）开始制定 C 语言标准，于 1989 年 12 月完成，并在 1990 年春天发布，称之为 ANSI C，有时也被称为 C89 或 C90。

## 搭建学习环境

### 安装 VMware

下载[学习版](https://www.52pojie.cn/thread-1026907-1-1.html)，安装步骤不多说了，只是有一点建议，也是我装软件的原则：能不装 C 盘就别装 C 盘。

### 下载系统镜像

### 安装系统镜像

1. VMware pro 15 安装完成后，启动，点击创建新的虚拟机；

![](https://img.imql.life/illustrations/FgdRlL67rlGMC-7iTc7AIGOPGSOl.png)

2. 选择典型，下一步；

![](https://img.imql.life/illustrations/FtuvsocoNkG7jCDF7s1htnuTHTNW.png)

3. 选择稍后安装操作系统，下一步；

![](https://img.imql.life/illustrations/Fr45RcoMPoajeMw5oFc8bC2EpxiQ.png)

4. 客户机操作系统选择 Linux，版本选择 Ubuntu 64 位，下一步；

![](https://img.imql.life/illustrations/FnHlhXuXR0OeJNFHzymriK5SKrnv.png)

5. 虚拟机名称和位置自定义，下一步；

![](https://img.imql.life/illustrations/FjXTWAcWRs2EXxkPak0wrbaJ5fbu.png)

6. 磁盘容量自定义。我这里就设为 60GB，下一步，完成；

![](https://img.imql.life/illustrations/FmhDAyMZCSoqrg0Lfwel2JSO4WR5.png)

7. 点击编辑此虚拟机，将处理器数量设为 4（一般为自己实体机处理器数量的一半）；

![](https://img.imql.life/illustrations/Fnk4EZlphETmAU0hVtUQ2k84o7U9.png)

8. 点击 CD/DVD (SATA)，选择使用 ISO 映像文件，浏览，选择 Ubuntu 18.04 LTS 系统的 ISO 映像文件，确定，点击开启此虚拟机，等待；

![](https://img.imql.life/illustrations/FswE05a1H_GIoK6G2PPmg-C5kTjh.png)

9. 选择中文(简体)，再选择安装 Ubuntu；

![](https://img.imql.life/illustrations/Fq4Cxjxbz6YJEu3afDEx6kdsvH2K.png)

10. 继续；

![](https://img.imql.life/illustrations/Fjs_JB5zYEE4CEKYwrFDiL0VrYq0.png)

11. 勾选最后一个，继续；

![](https://img.imql.life/illustrations/Ft5n3nOh9B9yTeLxlhrvu8Ba37R0.png)

12. 现在安装；

![](https://img.imql.life/illustrations/FmKW2aVOuuWVLw7Jt5NTuVaCd1hY.png)

13. 继续；

![](https://img.imql.life/illustrations/FrE7rEwTdvfN_0E4CnB6RtJ4cl4M.png)

14. 在地图上点击，选择 shanghai，继续；

![](https://img.imql.life/illustrations/FiTYo8hBHm3a0501fLrKfpuwUMRh.png)

15. 自定义信息，继续；

![](https://img.imql.life/illustrations/Fo6J-3z4X9D76yij2Kp8tFhYOFDX.png)

16. 等待；

![](https://img.imql.life/illustrations/FsxWnAXblxz8cERBuKkKxGGgfLSR.png)

17. 现在重启；

![](https://img.imql.life/illustrations/Ft9rn_1oWl9zgodsJ1wn7rlKaFzm.png)

18. 登录刚创建的用户。

![](https://img.imql.life/illustrations/FgRVUh1dUDLgewV7c9m1_sDLyGPf.png)

### 安装 VMware Tools

可以安装上 VMware Tools 让我们拥有最佳的 Ubuntu 18.04 LTS 操作体验，如在实体机上一般。首先点击左上方的虚拟机，再点击安装 VMware Tools，这时会在桌面出现一个 DVD，接下来具体安装过程如下：

![](https://img.imql.life/illustrations/lpXoTy7dkYYnSudn_5OiLBg3-tHJ.gif)

### 设置阿里镜像

1. 打开软件更新器；

![](https://img.imql.life/illustrations/FjwDjhW4ZKkpDxaaZPqXglyST501.png)

2. 一般会有更新提示，先不更新，点击设置；

![](https://img.imql.life/illustrations/FkKmb3wgybD6IQJjM4iVQsYmfSQX.png)

3. 点击 Ubuntu 软件，设置下载源；

![](https://img.imql.life/illustrations/Fi4frooS_f7gdi1TFb2_hgbZoUvX.png)

4. 点击其他站点，选择阿里云镜像站点，需要输入用户密码认证；

![](https://img.imql.life/illustrations/FldORXOOLV8d0HbuD_8LKUzf_lux.png)

5. 重新载入可用软件包列表；

![](https://img.imql.life/illustrations/FmsqcevGa02q7rOThARiM-RsJlqr.png)

6. 现在和以后就可以高速安装更新或软件包了，点击立即安装；

![](https://img.imql.life/illustrations/Fsg0pLxvXhnwDfKP7xVmpIvj_aOK.png)

### 美化自己的 Ubuntu 18.04 LTS

1. 右键点击桌面，在终端打开，输入以下命令回车，输入用户密码安装 gnome-tweak-tool 软件包；

```bash
sudo apt install gnome-tweak-tool
```

2. 火狐浏览器访问 [GNOME Shell Extensions](https://extensions.gnome.org)，点击安装该浏览器扩展；

![](https://img.imql.life/illustrations/FpIkm4qxJ7gSXR7asKl1rAlQZXLJ.png)

3. 刷新一下浏览器，这时会有错误信息，右键点击桌面，在终端打开，输入以下命令回车，输入用户密码安装 chrome-gnome-shell 软件包，再刷新一下浏览器，错误消失了；

```bash
sudo apt install chrome-gnome-shell
```

![](https://img.imql.life/illustrations/FulgjNMDks6dh6eKju1V7N0-dFA8.png)

4. 分别点击两个 GNOME Shell 扩展：User Themes 和 Dash to Dock，将它们都开启（即安装）；

![](https://img.imql.life/illustrations/FrklIXOv4aEhYGSHrKfkBLtfTELK.png)

5. 在安装完 Dash to Dock 时，你会发现侧边栏消失了，相信这是大多数人想要的效果；

![](https://img.imql.life/illustrations/FqooB653TSpyzqSqxrl0TVW_ghbU.png)

6. 打开优化；

![](https://img.imql.life/illustrations/FoFsmyuUUlfTXfFuJqQp-f5i5MAo.png)

7. 打开 Dash to Dock 的设置；

![](https://img.imql.life/illustrations/FhZer19pFB6fUPV3HFULpMAvsGZm.png)

8. 打开智能隐藏的设置；

![](https://img.imql.life/illustrations/Fs85G3Xghlr7UViNv9ZVzBTv51tM.png)

9. 勾选在全屏状态下启用，不勾选推压以显示......，调整显示超时时间为 0.2 秒，关闭窗口，此时，再打开火狐浏览器，当把鼠标移动到左侧，侧边栏自动显示，移走鼠标，侧边栏自动隐藏，相信这同样是大多数人想要的效果；

![](https://img.imql.life/illustrations/Fi5Rj2OuVaNPuCvYrnA1fsoPsPsO.png)

![](https://img.imql.life/illustrations/FtQjzsOjYpr5HJ3QTV2q03HFErYI.gif)

10. 打开火狐浏览器，进入[该网址](https://www.gnome-look.org/p/1275087/)下载 McMojave 主题，等待，确定；

![](https://img.imql.life/illustrations/FsF5JL9aiYjr5YzYnwfE3ieR8AD7.png)

11. 提取到下载中，点击显示文件；

![](https://img.imql.life/illustrations/FlH5XgyVtFUOujZKnTFgsDGgzX9I.png)

12. 右键，在终端打开；

![](https://img.imql.life/illustrations/FhK7m9_vp4bJXg7UxBmQ3qFccBWY.png)

13. 输入以下命令回车，输入用户密码，移动 Mojave-light 目录；

```bash
sudo mv Mojave-light/ /usr/share/themes/
```

14. 打开优化，选择 Mojave-light 主题，就能看到效果了；

![](https://img.imql.life/illustrations/FmFk5Kbu_QSRRaaqgeWatehyJCE-.gif)

15. [进入该网址](https://www.gnome-look.org/p/1305429/)，下载 McMojave-circle 图标，等待，确定；

![下载图标.png](https://cdn.nlark.com/yuque/0/2022/png/8391941/1643962978436-4eb611fc-612c-4525-b035-9d1606e35845.png#clientId=u9e62351f-20ea-4&crop=0&crop=0&crop=1&crop=1&errorMessage=unknown%20error&from=drop&id=u69a28e4b&name=%E4%B8%8B%E8%BD%BD%E5%9B%BE%E6%A0%87.png&originHeight=1080&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=299869&status=error&style=shadow&taskId=ud64c2509-8b3c-4c8a-af4d-841b5545539&title=)

16. 同上，提取到下载中，点击显示文件，右键，在终端打开，输入以下命令回车，输入用户密码，移动 McMojave-circle 目录；

```bash
sudo mv McMojave-circle/ /usr/share/icons/
```

17. 打开优化，选择 McMojave-circle 图标，就能看到效果了；

![](https://img.imql.life/illustrations/FpJwj4CUUM9mweU4sN4IEyUTmvFr.gif)

18. 有一个地方忘记了，打开优化，选择 shell 为 Mojave-light；

![](https://img.imql.life/illustrations/Ft_Faz2MxNh6Er1s6a3T09smyrhR.gif)

19. 可以在 Dash to Dock 设置中设置侧边栏的位置在底部；

![](https://img.imql.life/illustrations/Ft5DDuTokamYopU3bzj7yFY0JayX.png)

20. 最后，在优化->窗口中，设置标题栏按钮在左边，右键桌面更换个壁纸，至此，美化算是告一段落了。

### 安装 build-essential 软件包和 Vim 文本编辑器

右键点击桌面，在终端打开，输入以下命令回车，输入用户密码安装 build-essential 软件包。

```bash
sudo apt-get install build-essential
```

再输入以下命令回车，输入用户密码安装 Vim 文本编辑器。

```bash
sudo apt-get install vim
```

## 注释

如何注释应该是我们学习任何一门编程语言最先需要知道的，C 语言中有两种注释方式：

- 以`/*`开始`*/`结束的块注释（block comment）；
- 以`//`开始换行符结束的单行注释（line comment）；

## C 语言学习起步

右键点击桌面，新建一个学习文件夹 C Learning，点开，再新建文件夹（一），再点开，再新建文件夹 20200404 ，再点开，右键，在终端打开。

### 新建 hello_world.c 源文件、用 Vim 编辑并保存

输入以下命令新建 hello_world.c 源文件并用 Vim 打开：

```bash
vim hello_world.c
```

![](https://img.imql.life/illustrations/FkpYPmZfQL0n2hFP5WoZML01DrZ7.png)

按下 i 键进入插入模式，国际惯例，编写第一个程序：打印”Hello,World!“：

```c
#include <stdio.h>
int main(){
    printf("Hello,World!\n"); //print是打印的意思，f是format的简写，printf()函数的功能就是格式化输出
    return 0;
}
```

按下 ESC 键进入一般模式，再按”SHIFT+;“（即输入英文的分号）进入命令模式，输入 wq 命令（write and quit），这样源文件就保存了。

![](https://img.imql.life/illustrations/Flj0H7eIAr6rLQpOxl0XbOzGX-MO.gif)

### 编译

之后就是编译，输入以下命令回车执行（小技巧：打 hello_world.c 时，可以只打 h 再按 TAB 键，系统能自动匹配）：

```bash
gcc hello_world.c
```

输入以上命令后没有任何提示，别慌，这是正常的，在 Linux 中，没有消息就是好消息。可以输入以下命令(`ls -alF *`的别名）列出当前目录下有哪些文件和目录，./指的是当前目录，../指的是上一级目录，hello_world.c 是刚刚保存的 C 源文件，那这个“a.out\*”是什么呢？没错，就是刚刚编译出来的可执行文件（ 星号表示该文件为可执行文件）。

```bash
ll
```

![](https://img.imql.life/illustrations/Fh3kliZ30aPcT1A4H0_AA0FHRjmw.png)

### 运行

有了可执行文件，就可以运行了，输入以下命令执行就能打印出“Hello,World!”了。

```bash
./a.out
```

![](https://img.imql.life/illustrations/FrZLsFC6E_4iRSHLPiYf_Q-EMF5C.png)

### 小结

以上就是 C 学习的起步内容，下面就开始正式的学习，会总是需要用到上面提到的新建并编辑保存、编译和运行的相关命令，还有一个小技巧，可以使用键盘的方向键上和下在历史命令中切换。

## 做点计算

范例：做点计算（新建 compute.c）

```c
#include <stdio.h>

int main(){
    printf("12+34=%d\n",12+34); //%d为占位符，表示数据打印出来的格式应该是十进制整数的格式
    return 0;
}
```

打印结果：

```
12+34=46
```

除了做加法，当然还能做其他运算：

| 运算   | 运算符 |
| ------ | ------ |
| 加     | +      |
| 减     | -      |
| 乘     | \*     |
| 除     | /      |
| 取余数 | %      |
| 括号   | ()     |

## 变量

### 变量类型

C 语言是一种强类型的语言，所有的变量都必须有类型。

### 变量定义

变量定义的一般形式：

```
<类型名称> <变量名称>;
```

范例：定义变量 price，存放价格的 int 型数据，定义变量 payment，存放支付金额的 int 型数据

```c
int price;
int payment;
```

或

```c
int price,payment; //可以在一行中定义多个同类型的变量，有逗号分隔
```

### 标识符

标识符只能由字母、数字和下划线组成，数字不能出现在第一个字符的位置，标识符分为关键字，预定义标识符和用户自定义标识符，变量名称就属于用户自定义标识符。

### 赋值运算符

赋值也是一种运算，运算符为`=`，表示将右边的值复制一份赋给左边的变量，那么，这和数学中的等于号是一样的吗？当然不是，数学中的等于号表示的是相等的关系，C 语言也有表示相等关系的运算符，即`==`。

范例：使用赋值运算符初始化变量

```
int price=56;
int payment=100;
```

或

```
int price;
int payment;
price=56;
payment=100;
```

或

```
int price=56,payment=100;
```

### 用 scanf()函数初始化变量

范例：定义 price 和 payment 并用 scanf() 函数初始化它们

```c
int price,payment;
printf("请输入该商品价格（元）：");
scanf("%d",&price); //scan是扫描的意思，f同样是format的简写，scanf()函数的功能就是格式化扫描,扫描什么？扫描字符呗，以回车为结束符（不计入输入中）将输入的字符以十进制整数的格式解析，&price的意思就是将解析出来的值复制一份赋给price
printf("请输入支付的金额（元）：");
scanf("%d",&payment); //同上
```

### 变量的使用

范例：找零（新建 change.c)

```c
#include <stdio.h>

int main(){
    int price;
    int payment;
    printf("请输入该商品价格（元）：");
    scanf("%d",&price); //键盘输入的方式初始化price
    printf("请输入支付的金额（元）：");
    scanf("%d",&payment); //键盘输入的方式初始化payment
    int change=payment-price;
    printf("找零（元）：%d\n",change);
    return 0;
}
```

运行结果：

![](https://img.imql.life/illustrations/FkQEay6pd5C2ALlhFSWYW8zQ9QVz.gif)

### 没有初始化变量的后果

范例：没有初始化 payment（修改 change.c)

```c
#include <stdio.h>

int main(){
    int price;
    int payment;
    printf("请输入该商品价格（元）：");
    scanf("%d",&price); //键盘输入的方式初始化price
    int change=payment-price;
    printf("找零（元）：%d\n",change);
    return 0;
}
```

运行结果：

![](https://img.imql.life/illustrations/Fg51QkYLwmCuWlkivYRqz7mutMQC.gif)

什么！找零 2 亿多？？！！原来，变量在没有初始化，也就是刚一定义时，其实就是有值的，可是这个值只有计算机知道，在发生意想不到的问题之前，我们应该时刻注意变量在定义后一定要初始化。

## 常量

### 定义常量

变量定义的一般形式：

```c
const <类型名称> <常量名称>; //const是一个修饰符，是constant（常数）的简写，规定常量名称中的字母都为大写，这是命名规范
```

### 常量和变量的相同点和不同点

相同点：常量和变量都需要初始化。

不同点：常量在初始化后不能再被修改而变量可以。

### 常量的使用

在找零程序中，该商品，比如说一本书，它的价格就是 56 元，没必要总是输入 56，于是我们可以这么写：

范例：使用常量（修改 change.c)

```c
#include <stdio.h>

int main(){
    const int PRICE=56;
    int payment;
    printf("请输入支付的金额（元）：");
    scanf("%d",&payment); //键盘输入的方式初始化payment
    int change=payment-PRICE;
    printf("找零（元）：%d\n",change);
    return 0;
}
```

如果我们尝试去修改 PRICE 会如何？来试一下：

范例：尝试修改 PRICE（修改 change.c)

```c
#include <stdio.h>

int main(){
    const int PRICE=56;
    int payment;
    printf("请输入该商品价格（元）：");
    scanf("%d",&PRICE); //尝试修改PRICE
    printf("请输入支付的金额（元）：");
    scanf("%d",&payment); //键盘输入的方式初始化payment
    int change=payment-PRICE;
    printf("找零（元）：%d\n",change);
    return 0;
}
```

运行结果：

![](https://img.imql.life/illustrations/Fi8LEut1gqmdKSxurKUQUO3-7vhu.gif)

## 浮点型

美国人习惯用几英尺几英寸的方式描述自己的身高，如果遇到一个美国人告诉你他的身高为 5 英尺 7 英寸，他的身高应该是一米几呢？由于 1 英尺 = 12 英寸 = 0.3048 米，所以 5 英尺 7 英寸应该为 (5+7/12)\*0.3048 米，即 1.7018 米。来写个程序：

范例：长度换算（新建 length_conversion.c)

```c
#include <stdio.h>

int main(){
    printf("请分别输入身高的英尺和英寸，如5,7表示5英尺7英寸:");
    int foot; //英尺
    int inch; //英寸
    scanf("%d,%d",&foot,&inch);
    printf("身高是%f米\n",((foot+inch/12)*0.3048));
    return 0;
}
```

运行结果：

![](https://img.imql.life/illustrations/Fg4hg69KbI6JCmgHl24EzotJIMes.gif)

英尺似乎没发挥作用？这是怎么回事？原来，是由于 C 语言中相同数据类型的变量的计算结果仍然是该类型，inch 是 int 类型，12 是整形常量，默认是 int 类型，那么对于这个值永远都是在 0 到 11 范 围的 inch 来说，其与 12 的除法运算永远都是 int 类型，永远都会直接舍弃掉小数点后面的数据，永远都为 0，所以才会有以上的运行结果。

那么，以上程序该如何改进呢？这里，又紧接着引入一个知识点：在 C 语言中不同数据类型的变量的运算，是先将所有变量统一转化为一种表示范围最大的数据类型。

范例：长度换算（改）（修改 length_conversion.c)

```c
#include <stdio.h>

int main(){
    printf("请分别输入身高的英尺和英寸，如5,7表示5英尺7英寸:");
    int foot; //英尺
    int inch; //英寸
    scanf("%d,%d",&foot,&inch);
    printf("身高是%f米\n",((foot+inch/12.0)*0.3048)); //12是整形常量，默认是int类型，12.0是浮点型常量，默认是double类型
    return 0;
}
```

运行结果：

![](https://img.imql.life/illustrations/FqcEZt6KvEOvQVFJoIF1iduY9IMw.gif)

## 表达式

一个表达式是一系列运算符和算子的组合，用来计算出一个值。运算符（operator）是指进行运算的动作，比如加法运算符”+“，减法运算符”-“，算子（operand）是指参与运算的值，这个值可能是常数、变量和方法返回值等。

## 参考视频

[翁凯 C 语言（bilibili）](https://www.bilibili.com/video/BV19W411B7w1)

[【C 语言】《带你学 C 带你飞》（bilibili）](https://www.bilibili.com/video/BV17s411N78s)
