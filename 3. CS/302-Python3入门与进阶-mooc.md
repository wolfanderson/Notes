# Python3 入门与进阶 - mooc

**目录**

1 Python入门到学

2 Python环境安装

3 理解什么是代码与Python的基本类型

4 Python中表示“组”的概念与定义

5 变量与运算符

6 分支、循环、条件与枚举

7 包、模块、函数与变量作用域

8 Python函数

9 高级部分：面向对象

10 正则表达式与JSON

11 Python的高级语法与用法

12 函数式编程：匿名函数、高阶函数、装饰器

13 实战：原生爬虫

14 Pythonic与Python杂记


# 1 Python入门导学

Python 3.6

## Python的特点：简洁，易于学习

`Life if Simple, I Use Python.`

eg. 交换两个变量

- 其他语言

`temp = x
x = y
y = temp`

- Python

`x,y = y,x`

Python既有动态脚本的特性，又有面向对象的特点。

## Python的应用场景

- 爬虫

- 大数据与数据分析（Spark）

- 自动化运维与自动化测试

- Web开发：Flask，Django

- 机器学习：Tensor Flow, PyTorch

- 胶水语言：混合其他如C++、Java等编程

## Python之禅

*Simple is better than complex.*

*Now is better than never. Although never is often better than **right** now.*

## 本课程

- **特点**：细致与进阶

- **目的**：回归语言本质，打好基础

- **内容**：Python语言精粹

慕课手记、知乎专栏：@小楼昨夜又秋风

# 2 Python环境安装

1. Windows下一件环境安装包

2. Python 2.X 与 Python 3.X

官网下载安装，注意勾选`Add python to path.` 
可修改安装目录，如 `D:/Server/Python3.7`。

打开IDLE
```python
>>> print("Hello world")
Hello world
```

# 3 理解什么是代码与Python的基本类型

1. 什么是代码？

代码是现实世界事物在计算机世界中的映射。

2. 什么是写代码？

写代码是将现实世界中的事物，用计算机语言来描述。

## Python的基本数据类型

1. number: 数字 - 整数：int  浮点数：float

```python
>>> type(1)
<class 'int'>
>>> type(1.1)
<class 'float'>
>>> type(1+1.1)
<class 'float'>
>>> type(1*1.0)
<class 'float'>
>>> type(2/2)
<class 'float'>
>>> type(2//2)
<class 'int'>
```

**进制**

- 2进制： 0bXX  eg. 0b10

- 8进制：0oXX  eg. 0o10

- 16进制：0xXX  eg. 0x10

**进制转换**

- ->2进制：bin()

- ->8进制：oct()

- ->10进制：int()

- ->16进制：hex()

**bool** 布尔类型：真(Ture)，假(False)

```python
>>> int(True)
1
>>> int(False)
0
>>> bool(1)
True
>>> bool(0)
False
>>> bool(2)
True
>>> bool(1.1)
True
>>> bool('abc')
True
>>> bool('')
False
>>> bool([1,2,3])
True
>>> bool([])
False
>>> bool({1,1,2})
True
>>> bool({})
False
>>> bool(None)
False
```
**complex** 复数 j  eg. `36j`

2. str 字符串

- 如何表示字符串？

单引号，双引号，三引号

```python
>>> 'hello world'
'hello world'
>>> "hello world"
'hello world'
>>> 1
1
>>> '1'
'1'
>>> type(1)
<class 'int'>
>>> type('1')
<class 'str'>
>>> "let's go"
"let's go"
>>> 'let"s go'
'let"s go'
>>> 'let\'s go'
"let's go"
```

```python
>>> '''
hello world
hello internet
hello people
'''
'\nhello world\nhello earth\nhello people\n'

>>> '''hello world\nhello world\nhello world'''
'hello world\nhello world\nhello world'

>>> print('''hello world\nhello world\nhello world''')
hello world
hello world
hello world
>>> 

>>> 'hello \
world'
'hello world'
```

- **转义字符** 特殊的字符

	无法“看见”的字符

	与语言本身语法有冲突的字符

`\n` 换行

`\'` 单引号

`\t` 横向制表符

`\r` 回车（注意与换行的区别）

```python
>>> print('hello \n world')
hello 
 world
>>> print('hello \\n world')
hello \n world

>>> print('c:\north\northwest')
c:
orth
orthwest
>>> print('c:\\north\\northwest')
c:\north\northwest
>>> print(r'c:\north\northweat')
c:\north\northweat
```

- **字符串运算**

```python
>>> "hello"+"world"
'helloworld'
>>> "hello"*3
'hellohellohello'
```

```python
>>> "hello world"[0]
'h'
>>> "hello world"[3]
'l'
>>> "hello world"[5]
' '

>>> "hello world"[-1]
'd'
>>> "hello world"[-3]
'r'

>>> "hello world"[0:4]
'hell'
>>> "hello world"[0:5]
'hello'
>>> "hello world"[0:-1]
'hello worl'

>>> "hello world"[6:10]
'worl'
>>> "hello world"[6:11]
'world'
>>> "hello world"[6:20]
'world'

>>> "hello world"[6:-1]
'worl'
>>> "hello world"[6:0]
''
>>> "hello world"[6:-0]
''
>>> "hello world"[6:]
'world'

>>> "hello python java c# javascript php ruby"[6:]
'python java c# javascript php ruby'
>>> "hello python java c# javascript php ruby"[:-4]
'hello python java c# javascript php '
>>> "hello python java c# javascript php ruby"[-4:]
'ruby'

>>> r'C:\Windows'
'C:\\Windows'
>>> R'C:\Windows'
'C:\\Windows'
```

# 4 Python中表示“组”的概念与定义

- **列表 list**  []

```python
>>> type([1,2,3,4,5,6])
<class 'list'>
>>> type(['hello',"world",1,9,True,False])
<class 'list'>
>>> type([[1,2],[3,4],[True,False]])
<class 'list'>

>>> ["新月打击","苍白之瀑","月之降临","月神冲刺"][0]
'新月打击'
>>> ["新月打击","苍白之瀑","月之降临","月神冲刺"][3]
'月神冲刺'
>>> ["新月打击","苍白之瀑","月之降临","月神冲刺"][0:2]
['新月打击', '苍白之瀑']
>>> ["新月打击","苍白之瀑","月之降临","月神冲刺"][-1:]
['月神冲刺']

>>> ["新月打击","苍白之瀑","月之降临","月神冲刺"]+["点燃","虚脱"]
['新月打击', '苍白之瀑', '月之降临', '月神冲刺', '点燃', '虚脱']
>>> ["点燃","虚脱"]*3
['点燃', '虚脱', '点燃', '虚脱', '点燃', '虚脱']

>>> [['巴西','克罗地亚','墨西哥','喀麦隆'],['','','','',],[],[],[],[],[],[]]
[['巴西', '克罗地亚', '墨西哥', '喀麦隆'], ['', '', '', ''], [], [], [], [], [], []]
```

- **元组 tuple**  ()

```py
>>> type((1,2,3,4,5))
<class 'tuple'>

>>> type((1,'-1',True))
<class 'tuple'>

>>> type((1))
<class 'int'>

>>> type(('hello'))
<class 'str'>

>>> type((1))
<class 'int'>
>>> (1+1)*2
4
>>> type((1,))
<class 'tuple'>
>>> type(())
<class 'tuple'>
```

```py
>>> 'hello world'[0:8:2]
'hlow'

>>> 3 in [1,2,3,4,5,6]
True
>>> 10 in [1,2,3,4,5,6]
False
>>> 3 not in [1,2,3,4,5,6]
False

>>> len([1,2,3,4,5,6])
6

>>> max([1,2,3,4,5,6])
6
>>> min([1,2,3,4,5,6])
1

>>> max('hello world')
'w'
>>> min('hello world')
' '
>>> min('helloworld')
'd'
```

```py
>>> ord('w')
119
>>> ord('d')
100
>>> ord(' ')
32

>>> ord('1')
49
>>> ord('9')
57
>>> ord('A')
65
>>> ord('Z')
90
>>> ord('a')
97
>>> ord('z')
122
```

- **集合 set**  {}

>* 序列(str, list, tuple)是有序的，集合(set)是**无序**的。
>* 集合内元素**不重复**。

```py
>>> type({1,2,3,4,5,6})
<class 'set'>
>>> {1,2,3,4,5,6}[0]
Traceback (most recent call last):
  File "<pyshell#21>", line 1, in <module>
    {1,2,3,4,5,6}[0]
TypeError: 'set' object does not support indexing

>>> {1,1,2,3,3,4,5}
{1, 2, 3, 4, 5}
```

```py
>>> len({1,2,3})
3
>>> len({1,1,2,3})
3
>>> 1 in {1,2,3}
True
>>> 1 not in {1,2,3}
False

>>> {1,2,3,4,5,6} - {3,4}
{1, 2, 5, 6}

>>> {1,2,3,4,5,6} & {3,4}
{3, 4}

>>> {1,2,3,4,5,6} | {3,4,7}
{1, 2, 3, 4, 5, 6, 7}

>>> type({})
<class 'dict'>

>>> type(set())
<class 'set'>

>>> len(set())
0
```

- **字典 dict**

key  value  通过key关键字，找到value。

有很多个key和value,属于集合类型，但不是序列。

定义 `{key1:value1,key2:value2,key3:value3...}`

```py
>>> type({1:1,2:2,3:3})
<class 'dict'>
>>> {'Q':'新月打击','W':'苍白之瀑','E':'月之降临','R':'月神冲刺'}
{'Q': '新月打击', 'W': '苍白之瀑', 'E': '月之降临', 'R': '月神冲刺'}
>>> {'Q':'新月打击','W':'苍白之瀑','E':'月之降临','R':'月神冲刺'}['Q']
'新月打击'
>>> {'Q':'新月打击','Q':'苍白之瀑','E':'月之降临','R':'月神冲刺'}['Q']
'苍白之瀑'
>>> {'Q':'新月打击','Q':'苍白之瀑','E':'月之降临','R':'月神冲刺'}
{'Q': '苍白之瀑', 'E': '月之降临', 'R': '月神冲刺'}
>>> {1:'新月打击','1':'苍白之瀑','E':'月之降临','R':'月神冲刺'}
{1: '新月打击', '1': '苍白之瀑', 'E': '月之降临', 'R': '月神冲刺'}
>>> {1:'新月打击','1':'苍白之瀑','E':'月之降临','R':'月神冲刺'}
{1: '新月打击', '1': '苍白之瀑', 'E': '月之降临', 'R': '月神冲刺'}
```

**value**: str int float list set dict

**key**: 必须是不可变的类型；

```py
>>> {[1,2]:'新月打击','1':'苍白之瀑','E':'月之降临','R':'月神冲刺'}
Traceback (most recent call last):
  File "<pyshell#46>", line 1, in <module>
    {[1,2]:'新月打击','1':'苍白之瀑','E':'月之降临','R':'月神冲刺'}
TypeError: unhashable type: 'list'
>>> {(1,2):'新月打击','1':'苍白之瀑','E':'月之降临','R':'月神冲刺'}
{(1, 2): '新月打击', '1': '苍白之瀑', 'E': '月之降临', 'R': '月神冲刺'}
```

空的字典用 `{}` 定义，空的集合用 `set()` 定义。

- **小结：Python的基本数据类型**

>* 数字(Number)：
	整形		int
	浮点型	float
	布尔型   bool
	复数		complex
>* 组
	序列：有序，可用下标索引来访问，能切片操作[0:5]
		字符串   str     不可变
		列表		list     可变
		元组		tuple    不可变
	集合  set    无序，没有索引，不能切片
	字典  dict   key:value 键值对是其最基本的概念

# 5 变量与运算符

## 变量

```py
A = [1,2,3,4,5,6]
B = [1,2,3]
print(A*3 + B)

skill = ['星月打击','苍白之瀑']

three_leaf_grass < sanyecao < clover
```

**变量名命名规范**

1. 可由字母、数字、下划线组成，但首字母不能是数字；

2. 系统保留的关键字，不能用于变量命名；

3. 区分大小写；

4. 在python中，变量没有类型区别；

**变量赋值**

```py
>>> a=1
>>> b=a
>>> a=3
>>> print(b)
1

>>> a=[1,2,3,4,5]
>>> b=a
>>> a[0]=6
>>> a
[6, 2, 3, 4, 5]
>>> b
[6, 2, 3, 4, 5]
```

- int str tuple 值类型  (不可变)

- list set dict 引用类型  (可变)

```py
>>> b='hello'
>>> id(b)
56307296
>>> b=b+'python'
>>> id(b)
56371264

>>> a=[1,2,3]
>>> id(a)
49912688
>>> hex(id(a))
'0x2f99b70'
>>> a[0]='1'
>>> id(a)
49912688

>>> b=[1,2,3]
>>> b.append(4)
>>> b
[1, 2, 3, 4]
```

*tuple () 定义后不再变动； list [] 可改变*

```py
>>> a=(1,2,3,[1,2,4])
>>> a[2]
3
>>> a[3]
[1, 2, 4]
>>> a[3][2]
4
```

## 运算符

1. 算术运算符

`+ - * / // % **`

```py
>>> 'hello'+' world'
'hello world'
>>> [1,2,3]*3
[1, 2, 3, 1, 2, 3, 1, 2, 3]
>>> 3-1
2
>>> 3/2
1.5
>>> 3//2
1
>>> 5%2
1
>>> 2**2
4
>>> 2**3
8
>>> 2**5
32
```

2. 赋值运算符

`= += *= /= %= **= //=`

3. 比较（关系）运算符

`== != > < >= <=`

```py
>>> b=1
>>> b+=b>=1
>>> b
2
```

4. 逻辑运算符

操作与返回的都是bool类型

`and or not`

```py
>>> True and True
True
>>> True and False
False
>>> True or False
True
>>> not True
False
>>> not not True
True

>>> 1 and 1
1
>>> 'a' and 'b'
'b'
>>> 'a' or 'b'
'a'
>>> not 'a'
False

>>> [1] or []
[1]
>>> [] or [1]
[1]

>>> 1 and 0
0
>>> 0 and 1
0
>>> 1 and 2
2
>>> 2 and 1
1

>>> 0 or 1
1
>>> 1 or 0
1
>>> 1 or 2
1
>>> 2 or 1
2
```

- int float 0被认为是False，非0被认为是True

- str 空字符串被认为是False，非空字符串被认为是True

- [] 空的列表被认为是False，非空列表为True

5. 成员运算符

判断一个元素是否在另外一组元素里；

返回值为bool类型。

- in

- not in

```py
>>> a=1
>>> a in [1,2,3,4,5]
True
>>> b=6
>>> b in [1,2,3,4,5]
False
>>> b not in [1,2,3,4,5]
True

>>> b='h'
>>> b in 'hello'
True
>>> b in (1,2,3,4)
False
>>> b in {1,2,'h'}

>>> b='a'
>>> b in {'c':1}
False
>>> b=1
>>> b in {'c':1}
False
>>> b='c'
>>> b in {'c':1}
True
```

6. 身份运算符

返回值为bool型。

- is

- is not

```py
>>> a = 1
>>> b = 2
>>> a is b
False
>>> b = 1
>>> a is b
True
>>> a=1
>>> b=1.0
>>> a==b
True
>>> a is b
False
```

关系运算符 == 比较值是否相等；

身份运算符 is 比较两个变量的身份（内存地址 id）是否相等。

```py
>>> a={1,2,3}
>>> b={2,1,3}
>>> a==b
True
>>> a is b
False

>>> c=(1,2,3)
>>> d=(2,1,3)
>>> c == d
False
>>> c is d
False
```

*一切皆对象*

- 对象的3个特征：id(身份), value(值), tpe(类型)

判断类型，可以用 type(), 更好的是 isinstance(a,str).

```py
>>> a=1
>>> isinstance(a,str)
False
>>> isinstance(a,int)
True

>>> isinstance(a,(int,str,float))
True
>>> isinstance(a,(str,float))
False
```

7. 位运算符

把数字当作二进制数进行运算。

- & 按位与

- | 按位或

- ^ 按位异或

- ~ 按位取反

- << 左移动

- >> 右移动

```py
>>> a = 2
>>> b = 3
>>> a & b
2
>>> a | b
3
```

**表达式**(Expression)是运算符(oprator)和操作数(operand)所构成的序列。

```py
>>> a=1
>>> b=2
>>> c=3
>>> a+b*c
7
>>> a or b and c
1
```

- **运算符优先级**

1. **		指数（次幂）运算

2. ~ + -	补码，一元加减（+@，-&）

3. * / % //	乘法，除法，模数，地板除

4. + -

5. >> <<	向左、向右移位

6. &	按位与

7. ^ \|	按位异或，常规的"OR"

8. <= < > >=	  比较运算符

9. <> == !=		  等于运算符

10. = %= /= //= -= += \*= \*\*=	赋值运算符

11. is  is not    身份运算符

12. in  not in    成员运算符

13. not > and > or    逻辑运算符

**左结合**

- **在IDE中开发**

- file / new file / save

运行 `python hello.py`

**开发工具 IDE (Intergrated Development Environment)**： pycharm, vscode, sublime

VSCode 插件：https://marketplace.visualstudio.com/vscode

- 在vscode中运行python程序：

1. 右键文件，Open in Terminal / `python hello.py`

2. python 插件： python

优势：智能感知，断点调试。

# 6 分支、循环、条件与枚举

- if else, for, while

```py
# 单行注释 Ctrl+/
# 多行注释 Alt+Shift+A

# 流程控制语句
'''
条件控制 循环控制 分支
if else    for    while
选择性问题
'''
# mood = True
mood = False

if mood :
    print('go to left')
    # print('back away')
# print('back away')
else :
    print('go to right')
```

```py
a = 1
b = 2

if a > b :
    print('a')
else :
    print('b')
```

```py
'''
    程序说明
'''

ACCOUNT = 'qiyue'
PASSWORD = '123456'

# constant 常量：python中的常量并非真正的常量

print('please input account')
user_account = input()

print('please input password')
user_password = input()

if user_account == ACCOUNT and user_password == PASSWORD:
    print('success')
else:
    print('fail')

```

```py
# snippet 片段
# if 下拉框选择 if else
# 使用 tab 切换到下一个代码块
# Shift + tab 上一个

a = True

if a:
    print('')
else:
    print('')

for target_list in expression_list:
    pass #空语句/占位语句

@staticmethod
def funcname(parameter_list):
    pass
```

```py
a = input()

print('a is ' + a)

if a == 1:
    print('apple')
else:
    if a == 2:
        print('orange')
    else:
        if a == 3:
            print('banana')
        else:
            print('shopping')
```

```py
a = input()
#从终端中输入的数字被认为是字符串！
print(type(a))
print('a is ' + a)
a = int(a)
if a == 1:
    print('apple')
elif a == 2:
    print('orange')
elif a == 3:
    print('banana')
else:
    print('shopping')

#没有switch语句，可用字典方式
```

```py
a = 1
b = 0

# a 和 b 不可能同时为 False
if condition:
    pass
else:
    pass
    
a or b
```

# 7 包、模块、函数与变量作用域

# 8 Python函数

# 9 高级部分：面向对象

# 10 正则表达式与JSON

# 11 Python的高级语法与用法

# 12 函数式编程：匿名函数、高阶函数、装饰器

# 13 实战：原生爬虫

# 14 Pythonic与Python杂记

