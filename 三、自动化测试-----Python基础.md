---
title: 三、自动化测试-----Python基础
date: 2018-06-26 13:15:13
tags: CSDN迁移
---
  ```
class A(object):
    def add(self,a,b):
        return a+b
count=A()
print(count.add(3,5))
```
 一般创建类时会首先声明初始化方法**init**().   
 注意：**init**()的两侧是双下划线，当我们在调用该类时，可以用来进行一些初始化工作

 
```
class A(object):
    def __init__(self,a,b):
        self.a=int(a)
        self.b=int(b)

    def add(self):
        return self.a + self.b

count=A("4",5)
print(count.add())

```
 继承

 
```
class A(object):       
    def add(self,a,b):
        return a + b    
class B(A):
    def sub(self,a,b):
        return a-b
print(B().add(4,5))
```
 模组：就是类库或者模块   
 如导入时间模块

 
```
>>> import time
>>> print(time.ctime())

```
 也可以这么使用

 
```
>>> from time import ctime
>>> print(ctime())

```
 导入模块time所有内容

 
```
from time import *
print(ctime())
print("休眠两秒")
sleep(2)
print(ctime())

```
 可以查看模块帮助，如

 
```
>>> import time
>>> help(time)
```
 模块调用 

 模块调用既可以调用系统模块，也可以自己创建一个模块，然后通过另一个程序调用   
 比如：新建一个文件夹名为：project   
 在project中通过IDLE创建一个模块为pub.py，内容为：

 
```
def add(a,b):
    return a+b
```
 在创建一个调用pub.py的count.py，内容为：

 
```
from pub import add
print(add(4,7)
```
 完成自创模块的调用   
 运行后，发现project文件夹中多了_pycache_文件夹，是为了提高模块的加载速度，引用预编译模块，只要引用第三方模块，都会出现这个文件夹

 跨目录调用模块   
 导入sys ，然后添加路径sys.path.append(“路径地址“）

 
```
import sys
sys.path.append("./model")
from model import new_count
test=new_count.B()
```
 异常处理

 
```
try:
    open("abc.txt","r")
    print(aa)
except BaseException as msg:
    print(msg)
```
 不管是否有异常，finally语句都会被执行

 
```
try:   
    print(aa)
except BaseException as msg:
    print(msg)
finally:
    print("不管是否异常，我都会被执行")
```
 raise抛出异常

 
```
from random import randint
number=randint(1,9)
if number%2==0:
    raise NameError("%d is even" %number)
else:
    raise NameError("%d is odd" %number)
```
   
  