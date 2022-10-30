---

title: Python 从入门到实践（一）

trans: Python-Learning(1)

date: 2020-01-27 18:09:17

cover: https://img.imql.life/Python.png

tags:

- Visual Studio Code
- Python v3.8.1
- Windows

categories:

- Python 从入门到实践

---

在当今的环境下 Python 逐渐成为一门热门的语言，作为一门有着 30 年发展历史的编程语言，其在数据分析领域以及人工智能领域发挥着重要作用。Python 是基于 C 语言，一诞生就具备了完善的语法，其给程序员最直观的印象是——它的简洁性。

<!-- more -->

## Python 特点

1. 语法简单灵活；
2. 规范化代码；
3. Python 是一个开源项目，有着广泛的开发支持；
4. Python 是一门面向对象的编程语言；
5. Python 具有强大的可移植性；
6. Python 属于解释性的编程语言；
7. Python 是一个“胶水语言”；
8. Python 拥有良好的并发处理支持。

## 搭建 Python 学习环境

前往[ Python 官网](https://www.python.org/)下载最新版 Python，需要说明的是，Python2.x 和 Python3.x 之间存在较大差异，在开发中一般都使用 Python3.x，本次使用的版本为 3.8.1。

![](https://img.imql.life/illustrations/FgdfaGqrR6cjH22lbgixwgLZq8Zh.png)

下载完成后运行安装程序，勾选 Add Python 3.8 to PATH，点击 Customize installation，点击 Next，点击 Install，等待安装完成。按下 Windows+R 组合键，输入 CMD 进入命令行窗口，输入 python，发现可进入 Python 交互式环境，如下图。

![](https://img.imql.life/illustrations/Fsf2soGAVLjO1LBl4mYkyGI5-kVi.png)

文本编辑器到底哪家强？我推荐 Visual Studio Code。[前往官网](https://code.visualstudio.com/)，点击 Download for Windows，下载完成后运行安装程序，下一步即可，建议到下图这一步时勾选上这三个选项，等待安装完成。

![](https://img.imql.life/illustrations/FtgJapiUtV6KNboeLbd-S609dX43.png)

安装完成后进入 Visual Studio Code，进入扩展市场（左侧第五个图标），搜索 chinese，如下图，点击 Install 安装简体中文包，安装完成后点击 Restart Now，。

![](https://img.imql.life/illustrations/FsiLvii2kr0VhR3QbLivQO6eKm-N.png)

仍然点击左侧第五个图标，搜索 python，第一个就是微软官方的，如下图，安装。

![](https://img.imql.life/illustrations/ForBWJZeBzRXBzfc01SzOsRVj4AH.png)

## Python 学习起步

虽然 Python 拥有交互式环境，但是无论如何，程序是需要定义在源文件之中的，Python 源文件的后缀为 py。新建一个文件夹，名字自定义，例如 Python Learning，VS Code 中打开该文件夹，如下图（也可以直接右键点击 Python Learning，选择通过 Code 打开），VS Code 中新建文件，命名为 hello_world.py，文件中输入以下一行代码，Ctrl+S 保存。

```python
print("Hello,world!")
```

![](https://img.imql.life/illustrations/FmWyV2slAuq1sY9613fLDfHobBSc.png)

点击右上角运行图标，可看到学习任何一门编程语言时第一个编写的程序的运行结果，如下图。

![](https://img.imql.life/illustrations/FhsoNBTqKIbAgOna4Pildcnc4yVD.png)

## 注释

- 单行注释：`# [注释内容]`
- 多行注释：`'''[多行注释内容]'''`或`"""[多行注释内容]"""`

## 变量（对象）

Python 中的变量不需要声明，每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。

范例：使用变量（修改文件 hello_world.py）

```python
message = "Hello,world!"
print(message)
message = "Hello,ql!"
print(message)
```

打印结果：

```
Hello,world!
Hello,ql!
```

可以同时为多个变量赋值。

范例：为多个变量赋值（修改文件 hello_world.py）

```python
message1, message2 = "Hello,world!", "Hello,ql!"
print(message1)
print(message2)
```

打印结果：

```
Hello,world!
Hello,ql!
```

值得说明的是，如果我们比较熟悉面向对象的编程的话，Python 语言里面所有的变量严格意义上来讲应该被称为“对象”；

范例：定义变量但是不设置内容(新建文件 None.py)

```python
message = None # 空引用
print(message)
```

打印结果：

```
None
```

很多编程语言都会使用`;`作为每行程序的完结符，然而`;`在 Python 中被设计为可选符号，如果希望在一行定义多个变量，可用`;`。

范例：使用`;`对一行中的多个变量进行区分（新建文件 hello_ql.py)

```python
message = "Hello,world" ;print(message) ;message = "Hello,ql!" ;print(message)
```

打印结果：

```
Hello,world!
Hello,ql!
```

和其他语言一样，Python 中，我们在命名变量时也需要遵守一些规则和指南，违反规则将导致错误，遵守指南让你编写的代码更容易阅读和理解：

- 变量名只能包含字母、数字和下划线。变量名可以以字母或下划线开头但不能以数字开头；
- 变量名不能包含空格，但可用下划线代替；
- 不要将 Python 关键字用做变量名，注意将 Python 内置函数用做变量名时，虽然不会导致错误但将覆盖这些函数；
- 变量名应即简短又具有描述性。例如：name 比 n 好，student_name 比 s_n 好，name_length 比 length_of_persons_name;
- 慎用小写字母 i 和大写字母 O，因为它们可能被人错看成数字 1 和 0。

## 常用数据类型

在 Python 之中常用的数据类型包括：整数、浮点数、复数、布尔、字符串、列表、元组、字典和日期。

范例：通过 type() 函数查看数据类型(新建文件 type.py)

```python
message = "Hello,world!"
print(type(message))
```

打印结果：

```
<class 'str'>
```

"<class 'str'>"表示 message 变量为字符串类型。

### 整数和浮点数

范例：两个整数相除（新建文件 num.py)

```python
num_a = 10
num_b = 4
print(num_a/num_b)
```

打印结果：

```python
2.5
```

范例：获取数据类型（修改文件 num.py)

```python
num_a = 10
num_b = 4
print(num_a/num_b)
print(type(num_a))
print(type(num_b))
print(type(num_a/num_b))
```

打印结果：

```
<class 'int'>
<class 'int'>
<class 'float'>
```

### 复数

复数数据类型不能直接使用，需要通过 complex() 函数。

范例：使用复数（一）（新建文件 complex.py)

```python
num = complex(10,2) # 实部为10，虚部为2
print(num)
```

打印结果：

```
(10+2j)
```

范例：使用复数（二）（修改文件 complex.py）

```python
num = complex(10,2) # 实部为10，虚部为2
print(num)
print(num.real) # 获取实部
print(num.imag) # 获取虚部
print(num.conjugate()) # 获取共轭复数
```

打印结果：

```
(10+2j)
10.0
2.0
(10-2j)
```

### 布尔

“布尔”是 19 世纪一位英国数学家的名字，Python 中布尔的取值：`True`和`False`。

范例：使用布尔（一）（新建文件 boolean.py)

```python
flag = True # Python中的True是首字母大写的
if flag: # 分支语句
        print("Hello,world!")
```

打印结果：

```
Hello,world!
```

Python 是通过 C 语言开发的，Python 继承了布尔型值为 0 表示假，为非 0 表示真的特性。

范例：使用布尔（二）（修改文件 boolean.py)

```python
flag = 1 # 非0
if flag: # 分支语句
        print("Hello,world!")
```

打印结果：

```
Hello,world!
```

### 字符串

字符串是一个开发中最为重要的的概念，Python 中直接使用单引号`''`或双引号`""`进行字符串的定义，使用哪一种引号定义字符串都是一样的，但需统一，不同的引号可以嵌套。

范例：引号嵌套（新建文件 quotation_mark.py)

```python
message = '"Hello,world!"' # 使用单引号定义字符串
print(message)
message = "'Hello,ql!'" # 使用双引号定义字符串
print(message)
```

打印结果：

```
"Hello,world!"
'Hello,ql!'
```

可使用`+`进行字符串的拼接操作。

范例：字符串的拼接（新建文件 string.py)

```python
message = "Hello,world!,"+"Hello,ql!"
print(message)
```

打印结果：

```
Hello,world!,Hello,ql!
```

#### 常用转义字符串

| 符号  | 描述                       | 符号  | 描述                         |
| ----- | -------------------------- | ----- | ---------------------------- |
| \\    | 续航符，实现字符串多行定义 | \\n   | 换行                         |
| \\\\  | 等价于“\\”                 | \\v   | 纵向制表符                   |
| \\'   | 等价于单引号               | \\t   | 横向制表符                   |
| \\"   | 等价于双引号               | \\r   | 回车                         |
| \\000 | 空字符串                   | \\f   | 换页                         |
| \\b   | 退格                       | \\oyy | 八进制字符，如“\\o12:”为换行 |
| \\e   | 转义                       | \\xyy | 十进制字符，如“\\x0a”为换行  |

范例：使用转义字符串（新建文件 escape.py)

```python
message = "Python:\"Hello,world!\"\n\tPython:\"Hello,ql!\""
```

打印结果：

```
Python:"Hello,world!"
        Python:"Hello,ql!"
```

### 函数 input()

利用函数 input()，Python 可以接受通过键盘输入的字符串类型的数据

范例：通过键盘输入数据（新建文件 input.py）

```python
input_data = input("你的名字：") # 给出提示字符串
print("Python:Hello,"+input_data+"!")
```

打印结果：

```
你的名字：ql
```

```
你的名字：ql
Python:Hello,ql!
```

范例：获取输入类型（修改文件 input.py）

```python
input_data = input("你的名字：") # 给出提示字符串
print("Python:Hello,"+input_data+"!")
print(type(input_data))
```

打印结果：

```
你的名字：ql
```

```
你的名字：ql
Python:Hello,ql!
<class 'str'>
```

### 数据类型转换函数

| 函数          | 描述                       |
| ------------- | -------------------------- |
| int（数据）   | 将指定数据转为整形数据     |
| float（数据） | 将指定数据转为浮点型数据   |
| bool（数据）  | 将指定数据转为布尔型数据   |
| str（数据）   | 将指定数据转为字符串型数据 |

范例：int() 函数（一）（新建文件 int.py)

```python
str = "155"
temp = int(str)
print(temp)
print(type(temp))
```

打印结果：

```
155
<class 'int'>
```

如果字符串不是由规定字符组成，int.py 就会产生异常。

范例：字符串不是由规定字符组成（修改文件 int.py）

```python
str = "2BC9"
temp = int(str)
print(temp)
print(type(temp))
```

打印结果：

```
Traceback (most recent call last):
  File "d:/Python Learning/20200205/int.py", line 2, in <module>
    temp = int(str)
ValueError: invalid literal for int() with base 10: '2BC9'
```

范例：int() 函数（二）（修改文件 int.py)

```python
str = "199"
num_f = "199.6"
num_bol = True # True转为整形数据1
result = int(str) + int(num_f) + int(num_bol)
print(result)
print(type(result))
```

打印结果：

```
399
<class 'int'>
```

范例：int() 函数（三）（修改文件 int.py)

```python
num_a = int(input("请输入第一个整数："))
num_b = int(input("请输入第二个整数："))
result = num_a + num_b
print(num_a+"+"+num_b+"="+result)
```

打印结果：

```
请输入第一个整数：12
```

```
请输入第二个整数：13
```

```
请输入第一个整数：12
请输入第二个整数：13
Traceback (most recent call last):
  File "d:/Python Learning/20200205/int.py", line 4, in <module>
    print(num_a+"+"+num_b+"="+result)
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

使用`+`拼接任何数据与字符串时都需要先将任何数据转为字符串类型。

范例：改正以上错误（修改文件 int.py）

```python
num_a = int(input("请输入第一个整数："))
num_b = int(input("请输入第二个整数："))
result = num_a + num_b
print(str(num_a)+"+"+str(num_b)+"="+str(result))
```

打印结果：

```
请输入第一个整数：12
```

```
请输入第二个整数：13
```

```
请输入第一个整数：12
请输入第二个整数：13
12+13=25
```

### 格式化输出

在使用`+`拼接字符串时总是得先将所有数据转为字符串实在是太麻烦。Python 沿用了传统的格式化输出标记和格式化输出辅助标记。

#### 格式化输出标记

| 标记 | 描述                                 | 标记 | 描述                                 |
| ---- | ------------------------------------ | ---- | ------------------------------------ |
| %c   | 输出单个字符字符串                   | %s   | 输出字符串                           |
| %d   | 输出整形                             | %f   | 输出浮点型，可设置精度               |
| %e   | 以科学计数法格式输出，使用小写字母 e | %E   | 以科学计数法格式输出，使用大写字母 E |
| %g   | %f 和 %e 的简写                      | %G   | %f 和 %E 的简写                      |
| %u   | 输出无符号整型                       | %o   | 输出无符号八进制数                   |
| %x   | 输出无符号十六进制数                 | %X   | 输出无符号十六进制数（大写字母）     |

范例：格式化输出标记（新建文件 format1.py）

```python
age = 23
url = "https://ql-isaac.github,io"
qq = 834471527
message = "ql 今年 %d 岁，我的个人博客地址：%s，我的 qq 号码(十六进制)：0X%X。"%(age,url,qq)
print(message)
```

打印结果：

```
ql 今年 23 岁，我的个人博客地址：https://ql-isaac.github,io，我的 qq 号码(十六进制)：0X31BD0667。
```

#### 格式化输出辅助标记

| 标记    | 描述                   | 标记 | 描述                                                      |
| ------- | ---------------------- | ---- | --------------------------------------------------------- |
| \*      | 定义宽度或小数点精度   | #    | 在八进制数前面显示零（0），在十六进制数前面显示“0x”或“0X” |
| -       | 左对齐                 | 0    | 显示位数不足时填充 0                                      |
| +       | 在正数前面显示加号     | m.n  | m 设置显示总长度，n 设置小数位数                          |
| 空格    | 显示位数不足时填充空格 |      |                                                           |
| （var） | 映射变量（字典参数）   |      |                                                           |

范例：格式化输出辅助标记（一）（新建文件 format2.py）

```python
num_a = 192.121231311121231
num_b = 98.23
print("%f,%f"%(num_a,num_b)) # %f 默认保留小数点后六位数字
print("%5.2f,%10.2f"%(num_a,num_b))
print("%5.2f,%010.2f"%(num_a,num_b))
```

打印结果：

```
192.121231,98.230000
192.12,     98.23
192.12,0000098.23
```

范例：格式化输出辅助标记（二）（修改文件 format2.py）

```python
num_a = 192.121231311121231
num_b = 98.23
print("%(num_a)f,%(num_b)f"%vars()) # %f 默认保留小数点后六位数字
print("%(num_a)5.2f,%(num_b)10.2f"%vars())
print("%(num_a)5.2f,%(num_b)010.2f"%vars())
```

打印结果：

```
192.121231,98.230000
192.12,     98.23
192.12,0000098.23
```

### 函数 print()

默认情况下使用函数 print() 都会进行换行，如果不希望换行，可以使用“end“参数。

范例：使用“end“参数（新建文件 print.py）

```python
print("Python:Hello,world",end="!")
print("Hello,ql!",end="\n")
print("ql:Hello,Python!")
```

打印结果：

```
Python:Hello,world!Hello,ql!
ql:Hello,Python!
```

## 运算符

### 数学运算符

| 运算符 | 描述     | 范例             |
| ------ | -------- | ---------------- |
| +      | 加法计算 | 20 + 15 = 35     |
| -      | 减法计算 | 20 - 15 = 5      |
| \*     | 乘法计算 | 20 \* 15 = 300   |
| /      | 除法计算 | 20 / 15 =        |
| %      | 取模计算 | 10 % 3 = 1       |
| \*\*   | 幂运算   | 10 \*\* 3 = 1000 |
| //     | 整除计算 | 10 // 3 = 3      |

范例：数学运算符（一）（新建文件 arithmetic.py）

```python
result = (1 + 2) * (4 / 2)
print(result)
print(type(result)) # 只要进行了除法，返回的数据类型就是浮点型
```

打印结果：

```
6.0
<class 'float'>
```

范例：数学运算符（二）（修改文件 arithmetic.py）

```python
result = (1 + 2) * (4 // 2)
print(result)
print(type(result))
```

打印结果：

```
6
<class 'int'>
```

### 简化赋值运算符

| 运算符 | 范例      | 形如         |
| ------ | --------- | ------------ |
| +=     | a += b    | a = a + b    |
| -=     | a -= b    | a = a - b    |
| \*=    | a \*= b   | a = a \* b   |
| /=     | a /= b    | a = a / b    |
| %=     | a %= b    | a = a % b    |
| \*\*=  | a \*\*= b | a = a \*\* b |
| //=    | a //= b   | a = a // b   |

范例：字符串上使用乘法（新建文件 multiplication.py)

```python
message = "Hello,world!"
message *= 3
print(message)
```

打印结果：

```
Hello,world!Hello,world!Hello,world!
```

Python 中没有自增（`++`）和自减（`--`）运算符，因为 Python 中所有的变量都为对象，所有的数据类型都为引用数据类型，而自增（`++`）和自减（`--`）运算符是只适用于基本数据类型的。

### 关系运算符

| 运算符 | 描述         | 范例             |
| ------ | ------------ | ---------------- |
| ==     | 相等比较     | 1 == 1（True）   |
| ！=    | 不等比较     | 1 ！= 1（False） |
| >      | 大于比较     | 10 > 5（True）   |
| <      | 小于比较     | 10 < 20（True）  |
| >=     | 大于等于比较 | 10 >= 10（True） |
| <=     | 小于等于比较 | 20 <= 20（True） |

关系运算符除了能针对数值型数据进行比较之外，还能比较字符串，比较字符串实际上就是依次比较字符的编码。

范例：比较字符串（新建文件 string.py)

```python
print("ql" == "ql")
print("ql" > "Ql" > "QL")
```

打印结果：

```
True
True
```

如果想知道某单个字符字符串的编码，可使用 ord() 函数。

范例：查看某单个字符字符串的编码（新建文件 ord.py）

```python
print("小写的“l”的编码：%d，大写的“L”的编码：%d"%(ord("l"),ord("L")))
```

打印结果：

```
小写的“l”的编码：108，大写的“L”的编码：76
```

顺便说明一下数字和大小写字母的编码范围：

- 数字：”0“(48) ~ ”9“(57)
- 大写字母：”A“(65) ~ ”Z“(90)
- 小写字母：”a“(97) ~ “z”(122)

### 逻辑运算符

| 运算符 | 描述   |
| ------ | ------ |
| and    | 逻辑与 |
| or     | 逻辑或 |
| not    | 逻辑非 |

### 位运算符

| 运算符 | 描述       |
| ------ | ---------- |
| &      | 位与       |
| &#124; | 位或       |
| ^      | 位异或     |
| ~      | 位非       |
| <<     | 左移运算符 |
| >>     | 右移运算符 |

### 进制转换函数

| 函数      | 描述               |
| --------- | ------------------ |
| bin(数据) | 转换为二进制数据   |
| oct(数据) | 转换为八进制数据   |
| int(数据) | 转换为十进制数据   |
| hex(数据) | 转换为十六进制数据 |

### 身份运算符

Python 中所有的数据类型都为引用数据类型，id() 函数可以获取相应的内存地址。

范例：id() 函数（新建文件 id.py)

```python
num_a = 2
num_b = 1 + 1
num_c = 4 - 2
print("num_a 变量的地址：%d"%id(num_a))
print("num_b 变量的地址：%d"%id(num_b))
print("num_c 变量的地址：%d"%id(num_c))
```

打印结果：

```
num_a 变量的地址：1757145024
num_b 变量的地址：1757145024
num_c 变量的地址：1757145024
```

Python 中相等比较运算符`==`类似于 Java 中的`equals()`。

范例：内容相等比较（新建文件 equals.py)

```python
num_a = 2 # 整形
num_b =2.0 # 浮点型
print("整形变量地址：%d，浮点型变量地址：%d，两者内容是否相等：%s"%(id(num_a),id(num_b),(num_a == num_b)))
```

打印结果：

```
整形变量地址：1757145024，浮点型变量地址：11878208，两者内容是否相等：True
```

那么 Java 中的`==`在 Python 中用什么运算符替代呢？答案是身份运算符。

| 运算符 | 描述                 |
| ------ | -------------------- |
| is     | 判断是否引用同一内存 |
| is not | 判断是否引用不同内存 |

范例：内存地址相等比较（修改文件 equals.py)

```python
num_a = 2 # 整形
num_b = 2.0 # 浮点型
print("整形变量地址：%d，浮点型变量地址：%d，两者地址是否相等：%s"%(id(num_a),id(num_b),(num_a is num_b)))
```

打印结果：

```
整形变量地址：1757145024，浮点型变量地址：16400192，两者内容是否相等：False
```

## 分支结构

针对分支结构的实现，Python 里有三个关键字：`if`、`elif`（Python 单独提供了该关键字，同 else if）和`else`，三种语法：

- if 判断

```python
if <布尔表达式>:
    <语句块>
```

- if...else 判断

```python
if <布尔表达式>:
    <语句块>
else:
    <语句块>
```

- 多条件判断

```python
if <布尔表达式>:
    <语句块>
elif <布尔表达式>:
    <语句块>
elif <布尔表达式>:
    <语句块>
    <...>
else:
    <语句块>
```

不得不说说 Python 中的缩进，Python 根据缩进来判断代码行与前一个代码行的关系，类似于 C 和 Java 语言的大括号，PEP8 建议每级缩进都使用四个空格，这既可提高可读性，又留下了足够多的多级缩进空间。

范例：判断闰年（新建文件 leap_year.py)

```python
year = int(input("请输入一个年份："))
if (year % 4) == 0:
    if(year % 100) == 0:
        if(year % 400) == 0:
            print("%d 年是闰年"%(year)) # 整百年里能被400整除的是闰年
        else:
            print("%d 年不是闰年"%(year))
    else:
        print("%d 年是闰年"%(year)) # 非整百年里能被4整除的为闰年
else:
    print("%d 年不是闰年"%(year))
```

## 循环结构

循环结构指的就是某段代码重复地执行，在循环结构之中需要定义一个循环的条件，只有在满足循环条件时代码才执行，Python 中循环结构有两种：while 循环和 for 循环。

### while 循环

```python
while <循环条件>:
    <循环语句块>
    <修改循环条件>
```

或

```python
while <循环条件>:
    <循环语句块>
    <修改循环条件>
else:
    <循环条件不满足时执行的语句块>
```

范例：进行 1~100 的自然数的累加（新建文件 accumulation.py）

```python
sum = 0
num = 1
while num <= 100:
    sum = sum + num
    num += 1
print(sum)
```

打印结果：

```
5050
```

范例：打印 1000 以内的斐波那契数列（新建文件 fibonacci_sequence.py)

```python
num_a = 0
num_b = 1
while num_b < 1000:
    print(num_b,end="、")
    temp = num_b;
    num_b = num_a + num_b
    num_a = temp
```

### for 循环

| for 循环                              | for...else 循环                                                                   |
| ------------------------------------- | --------------------------------------------------------------------------------- |
| for <变量> in <序列>

 <循环语句> | for <变量> in <序列>

 <循环语句>

else:

 <循环语句执行完毕后的语句> |

## 序列

Python 在设计的过程中强调的一直是简洁性。在许多的编程语言中，都是首先利用了数组去描述多数据的存储，但是数组有长度固定，插入麻烦等缺点，因而才有了许多数据结构来满足我们的各种需求，Python 则帮我们封装了数组和许多数据结构，相应着重提出了序列这一概念，将能动态修改的内容统一称为序列，在 Python 之中字符串、列表、元组、字典都属于序列。

### 列表

直接使用一对中括号定义列表，可使用索引访问列表元素，从 0 开始。

范例：定义列表（新建文件 list.py）

```python
infos = ["C/C++","Java","Python"]
print(infos[0],end="、")
print(infos[1],end="、")
print(infos[2])
```

打印结果：

```
C/C++、Java、Python
```

#### 列表的特性

范例：空列表不等同于 None（新建文件 None.py）

```python
list_a = []
list_b = None
print("list_a的地址为 %d，类型为 %s"%(id(list_a),type(list_a))
print("list_b的地址为 %d，类型为 %s"%(id(list_b),type(list_b))
```

打印结果：

```
list_a的地址为 13626696，类型为 <class 'list'>
list_b的地址为 1453821160，类型为 <class 'NoneType'>
```

范例：在进行索引访问时不能越界（修改文件 list.py）

```python
infos = ["C/C++","Java","Python"]
print(infos[0],end="、")
print(infos[1],end="、")
print(infos[2])
print(infos[3])
```

打印结果：

```
C/C++、Java、Python
Traceback (most recent call last):
  File "d:/Python Learning/（一）/20200226/list.py", line 5, in <module>
    print(infos[3])
IndexError: list index out of range
```

范例：列表除了可以正向索引访问之外，还可以反向索引访问（修改文件 list.py）

```python
infos = ["C/C++","Java","Python"]
print(infos[-3],end="、")
print(infos[-2],end="、")
print(infos[-1])
```

打印结果：

```
C/C++、Java、Python
```

范例：通过列表保存多种数据类型（新建文件 python.py)

```python
infos = ["Python","简洁",["列表元素 1","列表元素 2","列表元素 3"]] # 数据的意义：编程语言（Python），特点（简洁），举例（列表）
print("编程语言：%s"%infos[0],end="、")
print("特点：%s"%infos[1],end="、")
print("举例：%s"%infos[2])
```

打印结果：

```
编程语言：Python、特点：简洁、举例：['列表元素 1', '列表元素 2', '列表元素 3']
```

范例：使用 for 循环迭代输出（修改文件 list.py）

```python
infos = ["C/C++","Java","Python"]
for pl in infos:
    print(pl)
```

打印结果：

```
C/C++
Java
Python
```

范例：使用 for 循环索引访问输出（修改文件 list.py）

```python
infos = ["C/C++","Java","Python"]
for index in range(len(infos)):
    print(infos[index])
```

打印结果：

```
C/C++
Java
Python
```

范例：根据索引修改数据内容（修改文件 list.py）

```python
infos = ["C/C++","Java","Python"]
infos[1] = "PHP"
print(infos[0],end="、")
print(infos[1],end="、")
print(infos[2])
```

打印结果：

```
C/C++、PHP、Python
```

范例：使用乘法（新建文件 multiply.py）

```python
infos = ["C/C++","Java","Python"] * 3
print(infos)
```

打印结果：

```
['C/C++', 'Java', 'Python', 'C/C++', 'Java', 'Python', 'C/C++', 'Java', 'Python']
```

范例：使用加法（新建文件 add.py)

```python
infos = ["C/C++","Java","Python"] + ["PHP"]
print(infos)
```

打印结果：

```
['C/C++', 'Java', 'Python', 'PHP']
```

#### 数据分片

列表的数据分片，即截取列表的一部分：

- 指定截取范围：`<列表>[<开始索引>:<结束索引>]`；
- 从指定索引一直截取到结尾：`<列表>[<开始索引>:]`；
- 从开头一直截取到指定索引：`<列表>[:<结束索引>]`；
- 设置截取步长：`<列表>[<开始索引>:<结束索引>:<步长>]`。

### 元组

### 序列统计函数

## 函数

## 函数深入

### lambda 表达式

lambda 表达式即 lambda 函数，

### 主函数

### callable()

callabl()

```
print("input()是否可以调用：%s" % callable(input))
def get_info
```
