title: 人生苦短，我用python
author: Gosthand
tags:
  - python
categories:
  - python
  - 学习笔记
date: 2018-12-10 08:12:00
---
## 我的Python学习笔记


##### 常用的关键词
###### Python标识符
在python里，标识符由字母、数字、下划线组成。

在python中，所有的标识符可以包括英文、数字以及下划线(_)，但不能以数字开头。

python中标识符是区分大小写的。

以下划线开头的标识符是有特殊意义的。以单下划线开头 <b>_foo</b> 的代表不能直接访问的类属性，需通过类提供的接口进行访问，不能用 <b>from xxx import *</b>而导入;

以双下划线开头的 <b>__foo</b> 代表类的私有成员；以双下划线开头和结尾的 <b>__foo__</b> 代表Python里特殊方法专用的标识，比如 <b>__init__()</b>代表类的构造函数。
Python可以同一行显示多条语句，，方法是用分号 <b>;</b>分开，如：

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
 
 class 
 
 from 
 
 print 
 
 continue
 
 global
 
 raise
 
 def 
 
 if 
 
 return 
 
 del 
 
 import 
 
 try 
 
 elif 
 
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
 
 以下代码将会执行

##### python变量