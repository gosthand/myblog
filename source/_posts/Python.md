title: 人生苦短，我用python
author: Gosthand
tags:
  - python
categories:
  - python
  - 学习笔记
date: 2018-12-10 08:12:00
---
# 我的Python学习笔记

##### 注意：
	
    Python中默认的编码格式是 ASCII 格式，在没修改编码格式时无法正确打印汉字，所以在读取中文时会报错。

解决方法为只要在文件开头加入 `# -*- coding: UTF-8 -*- `或者 `#coding=utf-8 `就行了

其中`=`两边不要空格，如：

```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-
print "你好，世界";
```
<!--more-->
##### 常用的关键词
###### Python标识符
在python里，标识符由字母、数字、下划线组成。

在python中，所有的标识符可以包括英文、数字以及下划线(`_`)，但不能以数字开头。

python中标识符是区分大小写的。

以下划线开头的标识符是有特殊意义的。以单下划线开头 <b>`_foo`</b> 的代表不能直接访问的类属性，需通过类提供的接口进行访问，不能用 <b>`from xxx import *`</b>而导入;

以双下划线开头的 <b>`__foo`</b> 代表类的私有成员；以双下划线开头和结尾的 <b>`__foo__`</b> 代表Python里特殊方法专用的标识，比如 <b>`__init__()`</b>代表类的构造函数。
Python可以同一行显示多条语句，，方法是用分号 <b>`;`</b>分开，如：

```Python
print 'hello';print 'world';
hello
runoob
```
###### python保留字符
所有 Python 的关键字只包含小写字母。
 and 
 
 exec 
 
 not 
 
 assert 
 
 finally 
 
 or 
 
 break 
 
 for 
 
 pass 
 
 class    ======》类
 
 from 
 
 print  ======》打印
 
 continue
 
 global
 
 raise
 
 def 
 
 if    ======》条件判断句
 
 return    ======》函数返回值
 
 del      ======》删除对象的引用   `del var1[,var2[,var3[....,varN]]]]`
 
 import    ======》引入对应的包、类、方法等
 
 try     ======》尝试，一般于  catch finally  一起使用，做异常处理
 
 elif    ======》else if  的python语法写法 。  否则如果、一般出现在多重判断中
 
 in   
 
 while
 
 else 
 
 is 
 
 with
 
 except 
 
 lambda 
 
 yield
 
 注意：
 
 &nbsp;&nbsp; &nbsp;&nbsp;Python的代码块不使用大括号来控制类，函数以及其他逻辑判断。Python 最具特色的是用缩进来写模块。
 
 缩进的空白数量是可变的，但是所有代码块语句必须包含相同的缩进空白数量，这个必须严格遵守。如下所示：
 
 ```Python
 if True:
     Print "True"
 else:
     Print "False"
 ```
 
 以下代码将会执行错误：
 
 ```python
 #!/usr/bin/python
# -*- coding: UTF-8 -*-
# 文件名：test.py

if True:
    print "Answer"
    print "True"
else:
    print "Answer"
    # 没有严格缩进，在执行时会报错
  print "False"
 ```

多行语句

Python语句中一般以新行作为语句的结束符。

但是我们可以使用斜杠`\`将一行的语句分为多行显示，如下所示：
```python
  total = item_one + \
        item_two + \
        item_three
```
语句中包含 [], {} 或 () 括号就不需要使用多行连接符。如下实例：
```python
days = ['Monday', 'Tuesday', 'Wednesday',
        'Thursday', 'Friday']
```
##### python注释
python注释以`#`开头，如：

```python
＃ 下面也是注释，，不过有一定含义。python解析器会对这个解析
# -*- coding: UTF-8 -*-   
# 这是python注释
print('你好') ＃这是注释
'''
这是多行注释，单引号
这是多行注释，单引号
这是多行注释，单引号
'''
"""
这也是多行注释，双引号
这也是多行注释，双引号
这也是多行注释，双引号
"""
```

###### 同一行显示多条语句
在python中，一行中使用多条语句，用`;`分隔，如：

```python
import sys; x = 'Hi, man!'; sys.stdout.write(x + '\n')
```

## python变量

Python 中的变量赋值不需要类型声明。

每个变量在内存中创建，都包括变量的标识，名称和数据这些信息。

每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。

等号`=`用来给变量赋值。

等号`=`运算符左边是一个变量名,等号`=`运算符右边是存储在变量中的值。例如：
```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
counter = 100 # 赋值整型变量
miles = 1000.0 # 浮点型
name = "John" # 字符串
 
print counter
print miles
print name
```
### python 标准数据类型类型
* Numbers （数字）
* String (字符串)
* List (列表)
* Tuple (元组)
* Dictionary (字典)

#### python 数字

python中数字类型用于存储数值。 他们是不可改变的数据类型，这意味着改变数字数据类型会分配一个新的对象。
当你指定一个值时，Number对象就会被创建：
```python
var1 = 1
var2 = 2
```
python支持四种不同的数字类型：
* int (有符号整型)
* long (长整型［也可以代表八进制和十六进制］)
* float （浮点数）
* complex  (复数)