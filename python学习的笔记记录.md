---
title: python学习的笔记记录
date: 2018-05-28 15:02:37
tags: CSDN迁移
---
  ```
# months=["January","February","March","April","May","June","July","August","September","October","November","December"]
# ending=["st","nd","rd"]+17*["th"]  +["st","nd","rd"]+7*["th"]+["st"]
# year=input("year:")
# month=int(input("month(1-12):"))
# day=int(input("day(1-31):"))
# # month_nmuber=int(month)
# # day_number=int(day)
# month_name=months[month-1]
# ordinal=str(day)+ending[day-1]
# print(month_name +" "+ordinal+"."+year)

# lucky_number=[0,1,2,3,4,5,6,7,8,9]
# print(lucky_number[0])
# print(lucky_number[4])
# print("----------------")
# print(lucky_number[0:3])
# print(lucky_number[4:8])
# print(lucky_number[-3:-1])
# print(lucky_number[-3:])
# print(lucky_number[:])
# print(lucky_number[7:11])
# print(lucky_number[0:10:2])
# print(lucky_number[::2])
# print(lucky_number[::-3])

# print([1,2,3]+[4,5,6])
# print("hello "+"world")
# print([1,22,3]+[" world"])
# print("python "*5)
# print(["python"]*5)

# student_name=["bale","bob"]
# print("bale" in student_name)
# name1=input("please your name:")
# print(name1 in student_name)

# number=[100,200,400]
# student_name=["aob","alice","aiba"]
# print(max(number))
# print(min(number))
# print(len(number))
# print("-----------")
# print(len(student_name))
# print(max(student_name))
# print(min(student_name))

# print(list("Bob"))
#修改元素
# x=[1,2,3]
# x[1]=5
# print(x)

# names=["a","b","c"]
# names.append("d") #增加一个元素
# print(names)
# names.extend(["d","e"]) #增加多个元素
# print(names)
# names.append(["d","e"])
# print(names)
# names.insert(1,"g")
# print(names)

# x=[1,2,3]
# #x.remove(2)#remove()放的是删除指定的元素
# print(x)
# names=["bob","liba","toney"]
# names.remove("liba")
# print(names)
# del x[2]
# print(x)
# numbers=[1,2,3,4,5,6,7]
# numbers.pop() #pop()默认弹出末尾，指定索引填出
# print(numbers)
# numbers.pop(2)
# print(numbers)

# lstr=["a","b","c"]
# print(lstr)
# lstr[2:]=list("de")
# print(lstr)
# lstr[2: 1]="f"
# print(lstr)
# lstr[2:4]=["d","g"]
# print(lstr)

# names=["alice","liba","tony"]
# if "alice" in names:
#     print(True)
# else :
#     print(False)

# print(names.index("liba"))

# numbers=[1,2,3,4,1]
# print(numbers.count(1)) #count()计算某元素在列表中出现的次数
# numbers.reverse() #reverse()将元素进行倒序排
# # print(numbers.reverse())
# print(numbers)

# numbers=[90,2,44,4,5]
# numbers.sort()
# print(numbers)
# x=[90,2,44,4,5]
# y=x.sort()
# print(x)
# print(y)
# print("------")
# x=[90,2,44,4,5]
# y=x[:]
# x.sort()
# print(x)
# print(y)
# print("---------------")

# x=[90,2,44,4,5]
# y=x
# x.sort()
# print(x)
# print(y)
# print("---------------")

# x=[90,2,44,4,5]
# y=sorted(x)
# print(x)
# print(y)

# x=list("list")
# print(x)
# print(tuple([1,2,3])) #tuple()将字符或者列表抓换成元组
# print(tuple("hello!"))
# names=["liba","tom"]
# print(tuple(names[1]))

# customer_info=[["alice",10001],["liba",10002],["tom",10003]]
# for customer in customer_info:
#     print(customer)

# print(customer_info[0])
# print(customer_info[1][1])

# sentence="price of eggs:%d"
# sentence="price of eggs: %x"
# print(sentence % 42)
# print("price of eggs:%d" % 42)
# print(sentence % 42)
# import math
# print("pi:%f......" % math.pi)
# from math import pi
# print("%11f" % pi)
# print("%10.2f" % pi)
# print(pi)
# print("%.2f" % pi)
# print("%.5s" % "python is great")
# print("%*.*s" % (7,6,"python is great"))
# print("%.*s" % (6,"python is great"))
# from math import pi
# print("%010.2f" % pi)
# print("%010f" % pi)
# print("%10f" % pi)
# print("%-10.2f" %pi)
# print("%+10.2f" %pi)
# print(("% 5d" % 10)+"\n"+("% 5d")% -10)
# print(("%+5d" % 10)+"\n"+("% 5d")% -10)

# sentence="the python is great!"
# print(sentence.find("python"))
# print(sentence.find("python",9))
# print(sentence.find("python",3,10))

# studenn_names=["alice","tom","liba"]
# print("+".join(studenn_names))
# numbers=["1","3","4"]
# print("-".join(numbers))
# dirs=(" ","home","lihua")
# print("/".join(dirs))
# print("c:"+"\\".join(dirs))

# sentence="hello world"
# print(sentence.split(" "))
# numbers="1+2+3+4"
# print(numbers.split("+"))
# print("/home/bob".split("/"))

# student_name="Alice"
# print(student_name.lower())
# student_names=["Alice","boob","tom"]
# if student_name.lower() in student_names[0].lower():
#     print(True)
# else:
#     print(False)

# sentence="this is a apple or apple"
# print(sentence.replace("apple","pear",1))

# student_name = " bob "
# names=["Alice" ,"bob","tom"]
# student_name_strip = student_name.strip()
# print(student_name_strip)
# if student_name_strip.lower() in names :
#     print(True)
# else:
#     print(False)

# lstr="****** sparming **** for !!!!**********?"
# print(lstr.strip("!*?"))

# lstr="this is python"
# oldsub="thi"
# newsub="ABC"
# trantab=lstr.maketrans(oldsub,newsub)
# print(lstr.translate(trantab))

# phonebook={"Alice":"1234","Bela":"23457"}
# print(phonebook)
# print(phonebook["Alice"])

# phonebook=[("Alice","1234"),("bob","789")]
# d=dict(phonebook)
# print(d)
# d["liba"]="88888"
# print(d)
# d["Alice"]="4321"
# print(d)

# phonebook={"Alice":"1234","Bela":"23457"}
# print(len(phonebook))
# print(phonebook["Alice"])
# phonebook["Bela"]="6789"
# print(phonebook)
# del phonebook["Bela"]
# print(phonebook)
# if "Alice" in phonebook:
#     print(True)
# else:
#     print(False)

# x={}
# y=x
# x["key"]="value"
# print(x)
# print(y)
# x={}
# print(x)
# print(y)
# print("字典的clear方法")
# x={}
# y=x
# x["key"]="value"
# print(x)
# print(y)
# x.clear() #clear（） 清空原有字典，无返回值或者返回为null
# print(x)
# print(y)

# student_info={"Alice":"12345","Bob":["55555","Boy"]}
# print(student_info)
# copy_student_info=student_info.copy() #copy()原字典值不变
# copy_student_info["Alice"]="1111"
# print(copy_student_info)
# print(student_info)
# print("******************")
# copy_student_info["Bob"].remove("55555") #remove（）原字典值改变
# print(copy_student_info)
# print(student_info)

#deepcopy()
# from copy import deepcopy
# d={}
# d["names"]=["Alice","Bela"]
# print(d)
# c=d.copy()
# dc=deepcopy(d)
# d["names"].append("Bob")
# print(d)
# print("***************")
# print(c)
# print(d)
# print(dc)

# names={"Alice":"1234"}
# print(names)
# print(names.get("Alice"))
# print(names.get("Bob","Bob is not exist"))

# names={"Alice":"1234","bob":"3333","tom":"44444"}
# print(names.keys())

# names={"Alice":"1234","bob":"3333","tom":"44444"}
# print(names.pop("Alice"))#pop()获取键对应的值，同时删除键对应的项删除
# print(names)

# names={"Alice":"1234","bob":"3333","tom":"44444"}
# # names=[1,2,3,4]
# # names.pop(1)
# names.popitem()#随机弹出键值对
# print(names)

# names={}
# names.setdefault("Alice","Liba")
# print(names)
# names["Alice"]="111"
# print(names)
# names.setdefault("Alice","dddd")
# print(names)

# names={"Alice":"1234","bob":"3333","tom":"44444"}
# cnames={"bob":"9999999999"}
# names.update(cnames)
# print(names)
# print("**********")
# cnames={"Bob":"0000"}
# names.update(cnames)
# print(names)

# print("Hello world")
# name="Bela"
# print("your name is:",name)
# print(1,2,3)
# print((1,3,4))
# age=19
# print(name,"age is :",age)
# print(name+"age is :"+str(age))

# import math
# print(math.pi)
# from math import pi
# print(pi)
# from math import *
# import math as tmath
# print(tmath.pi)

# x,y,z=1,2,3
# print(x,y,z)
# a=b=c=1
# print(a,b,c)
# values=1,2,3
# print(values)
# x1,x2,x3=values
# print(x1,x2,x3)
# name=name2="bela"
# print(name,name2)

# x=2
# print(x)
# x=x+2
# print(x)
# x+=2
# print(x)
# x *=2
# print(x)

# names=["alice","bela"]
# if "alice" in names:
#     print(True)
# else:
#     print(False)

# num1=int(input("please your first number:"))
# num2=int(input("please your second number:"))
# if num1<num2:
#     print(num1,"<",num2)
# if num1> num2:
#     print(num1,">",num2)
# if num1==num2:
#     print(num1,"=",num2)
# if num1!=num2:
#     print(num1,"!=",num2)

# num1=int(input("please your first number:"))
# if num1>=10:
#     print(num1,">10")
# elif num1>=5:
#     print("5<",num1,"<10")
# elif num1>=1:
#     print("1<",num1,"<5")
# else:
#     print(num1,"<0")

# age=int(input("Enter your age:"))
# if age>=18:
#     grade=int(input("Enter your grade:"))
#     if grade>=60:
#         print("you gan play this game!")
#     else:
#         print("sorry,you can not play this game")
# else:
#     print("sorry,you can not play this game!")

# age=int(input("Enter your age:"))
# grade=int(input("Enter your grade:"))
# if age>=18 and grade>=60 :
#     print("you can play this game!")
# else:
#     print("you can't play this game!")

# age=int(input("Enter your age:"))
# grade=int(input("Enter your grade:"))
# if age>=18 or grade>=60 :
#     print("you can play this game!")
# else:
#     print("you can't play this game!")

# age=int(input("Enter your age:"))
# if not (age<18):
#     grade=int(input("Enter your grade:"))
#     if grade>=60:
#         print("you gan play this game!")
#     else:
#         print("sorry,you can not play this game")
# else:
#     print("sorry,you can not play this game!")

# num1=10
# assert num1<3 #assert 断言
#while 默认为真
# name=""
# while not name:
#     name=input("please your name:")
# print("hello's %s",name)

# for looper in [1,2,3,4]:
#     print(looper)

# d={"num1":1,"num2":2,"num3":3}
# for  key in d:
#     print(key,"=",d[key])

# for number in range(5):
#     print(number)

# for number in range(1,10,3):
#     print(number)

# names=["Alice","Liba","Tom","Bob"]
# ages=[1,2,3,4]
# # print(len(names))
# # for i in range(len(names)):
# #     print(names[i],"is",ages[i],"years")
# for name,age in zip(names,ages):
#     print(name,"is",age,"year")

# names=["Alice","Liba","Tom","Bob"]
# index=0
# for name in names:
#     if "ob"in name:
#         names[index]="huahua"
#     index+=1
# print(names)

# for i in range(5):
#   print("******************")
#   print("i=",i)
#   if i==3 :
#     continue
#   print("hello everyone")

# for i in range(5):
#   print("******************")
#   print("i=",i)
#   if i==3 :
#     break
#   print("hello everyone")

# multiplier=5
# for i in range(5):
#     print(i,"*",multiplier,"=",i*multiplier)

# for multiplier in range(4,7):
#     for i in range(1,5):
#         print(i,"*",multiplier,"=",i*multiplier)
#     print("*********")

# numStars=int(input("How many stars you want?"))
# for i in range(1,numStars):
#     print(" * ",end="")

# numLines=int(input("How many lines you want?"))
# numStars=int(input("How many stars you want?"))
# for line in range(numLines):
#     for i in range(numStars):
#         print(" * ",end="")
#     print()
#     print("===========")

# numBlock=int(input("How many block you want?"))
# numLines=int(input("How many lines you want?"))
# numStars=int(input("How many stars you want?"))
# for block in range(numBlock):
#     for line in range(numLines):
#         for i in range(numStars):
#             print(" * ",end="")
#         print()
#     print("===========")

# fibs=[0,1]
# num=int(input("Enter a num:"))
# for i in range(num):
#     fibs.append(fibs[-2]+fibs[-1])
# print(fibs)
#
#函数的格式
# def printMyaddress():
#     print("bela")
#     print("bela age is 20")
#     print()
# printMyaddress()

# def fibs(num):
#     fib=[0,1]
#     # num=int(input("Enter a num:"))
#     for i in range(num):
#         fib.append(fib[-2]+fib[-1])
#     print(fib)
# fibs(int(input("enter a num:")))

# def printMyaddress(name,age):
#     print("your name is:",name,age)
#     print(name,"age is:",age)
#     print()
# printMyaddress("Bela",20)
# printMyaddress("Leo",18)

# def studentInfo(name,age,city):
#     print("the student name is:",name)
#     print("the student age is :",age)
#     print("the student city is :",city)
# studentInfo("bela",20,"beijing")

# def calculateTax(price,tax_rate):
#     "计算打车的费用"#函数文档化位置在函数名称冒号之后，代码块第一行print("the student age is :",age)
#     taxToal=price*tax_rate
#     return taxToal
# print(calculateTax(3,8))
# print(calculateTax.__doc__)

# import math
# print(math.sqrt.__doc__)

# def calculateTax(tax_rate,price):
#     "计算打车的费用"#函数文档化位置在函数名称冒号之后，代码块第一行print("the student age is :",age)
#     taxToal=(price+1)*tax_rate
#     return taxToal
# # print(calculateTax(3,8))
# print(calculateTax.__doc__)
# print(calculateTax(price=3,tax_rate=8))

# def calculateTax(price=3,tax_rate=8):
#     "计算打车的费用"#函数文档化位置在函数名称冒号之后，代码块第一行print("the student age is :",age)
#     taxToal=(price+1)*tax_rate
#     return taxToal
# print(calculateTax())
# print(calculateTax(4))
# print(calculateTax(4,9))
# print(calculateTax(tax_rate=10))

#收集参数：不确定参数的具体个数 用*表示
# def many_params(*nums):
#     print(nums)
# many_params("Hello")
# many_params(1,2,3,4,5)

# def studentInfo(name,*nums):
#     print(name,nums)
# studentInfo("leno","liha",12,"hello")

# def calculateTax(price,tax_rate):
#     print(price)
#     taxToal=(price)*tax_rate
#     return taxToal

# my_price=int(input("Enter a price:"))
# totalPrice=calculateTax(my_price,8)
# print("price=",my_price,"totalPrice=",totalPrice)
# print(price) #报错

# def calculateTax(price,tax_rate):
#     # print(price)
#     my_price=100
#     print("Fountion inside:",my_price)
#     taxToal=(price)*tax_rate
#     return taxToal

# my_price=int(input("Enter a price:"))
# totalPrice=calculateTax(my_price,8)
# print("price=",my_price,"totalPrice=",totalPrice)
# print("outside",my_price)

# def calculateTax(): #递归简单案例，程序会报错
#     return calculateTax()
# calculateTax()

# n的阶乘
# def calcuate(n):
#     result=n
#     for i in range(1,n):
#         result*=i
#     return result
# print(calcuate(3))

# def calcuate(n):
#     if n==1:
#         return 1
#     else:
#         return n*calcuate(n-1)

# print(calcuate(3))

#self是个默认的参数，self参数是对于对象自身的引用
# class Person():
#     def setName(self,name): 
#         self.name=name
#     def getName(self,name):
#         self.name=name
#     def greet(self):
#         print("Hello ! i am %s"%self.name)
# foo=Person()
# bar=Person()
# foo.setName("Bela")
# bar.setName("Alice")
# # print(foo.greet())
# # print(bar.greet())
# print(foo) #对象foo在内存中存在的地址

# #__init__当类使用初始化方法后，对象在实例化时，必须将init中的参数一并赋予
# class Person():
#     def __init__(self,name):#使用初始化方法
#         self.name=name
#     def getName(self):
#         return self.name
#     def greet(self):
#         print("the name is %s"%self.name)
# foo =Person("bela")
# print (foo.greet())

# class Person():
#     age=18 #属性
#     def __init__(self,name):#使用初始化方法
#         self.name=name
#     def getName(self):
#         return self.name
#     def greet(self):
#         print("the name is %s"%self.name)
# foo =Person("bela")
# print (foo.getName())
# print(foo.age)


# #私有变量（是__双下划线）定义，类中的私有变量、外部是无法直接访问的；可以通过方法来访问私有变量或改变私有变量
# class Person():
#     __age=18
#     def __init__(self,name):#使用初始化方法
#         self.name=name
#     def getName(self):
#         return self.name
#     def setAge(self,newage):
#         self.__age=newage
#     def greet(self):
#         print("the age is %s"%self.__age)
# foo =Person("bela")
# print (foo.getName())
# print(foo.greet())
# foo.setAge(30)
# print(foo.greet())

# class Person():
#     name=""
#     age=0
#     __weight=0 #私有变量

#     #定义初始化方法
#     def __init__(self,n,a,w):
#         self.name=n
#         self.age=a
#         self.__weight=w

#     def speak(self):
#         print("%s 说：我今年%d 岁，%d斤" % (self.name,self.age,self.__weight))

# #实例化
# p=Person("Bela",4,30)
# print(p.speak())
# print(p.name)
# #print(p._weight) #私有变量无法通过该方法进行访问

# #继承案例一
# class Animal():
#     def run(self):
#         print("animal is running.......!!!")
# class Cat(Animal):
#     pass #代码桩
# class Dog(Animal):
#     pass
# #实例化
# fcat=Cat()
# fdog=Dog()
# print(fcat.run())
# print(fdog.run())


# #继承案例二
# class Person():
#     #定义属性
#     name=""
#     age=0
#     __weight=0 #私有变量

#     #定义初始化方法
#     def __init__(self,n,a,w):
#         self.name=n
#         self.age=a
#         self.__weight=w

#     def speak(self):
#         print("%s 说：我今年%d 岁，%d斤" % (self.name,self.age,self.__weight))

# #定一有个student类，继承person
# class Student(Person):
#     grade=""
#     def __init__(self,n,a,w,g):
#         Person.__init__(self,n,a,w)
#         self.grade=g
#     def speak(self):
#         print("%s 说：我今年%d 岁，读%s年级" % (self.name,self.age,self.grade))
# s=Student("Bela",4,30,1)
# print(s.speak())


# #继承案例三 多继承
# class Animal():
#     def run(self):
#         print("animal is running.......!!!")
# class Cat():
#     def call(self):
#         print("miao.....miao...!!")
# class Smallcat(Animal,Cat):
#     pass
# #实例化
# foo=Smallcat()
# foo.run()
# foo.call()

# #继承案例四 多个父类中同样的方法，从做往右检索类，看是否包含所调用的方法，首先检索到的被调用
# class Animal():
#     def run(self):
#         print("animal is running.......!!!")
# class Cat():
#     def run(self):
#         print("cat is running........!!")
#     def call(self):
#         print("miao.....miao...!!")
# class Smallcat(Cat,Animal):
#     pass
# #实例化
# foo=Smallcat()
# foo.run()
# foo.call()


#多态：不同的类有同样的方法，但是方法的行为不同
# class Animal():
#     def run(self):
#         print("animal is running.......!!!")
# class Cat():
#     def run(self):
#         print("cat is running........!!")
#     def call(self):
#         print("miao.....miao...!!")
# class Smallcat(Cat,Animal):
#     pass
# #实例化
# foo=Smallcat()
# foo.run()
# foo.call()

# class People():
#     #定义属性
#     name="Bela"
#     #定义一个方法
#     def getName(self):
#         print("Hello",self.name)
# #类的引用
# print(People.name)
# #类的实例化
# p=People()
# print(p.name)

# class People():
#     #定义属性
#     name="Bela"
#     #定义一个方法
#     def getName(self):
#         print("Hello",self.name)
# print(People.__name__)


# class People():
#     #定义属性
#     name="Bela"
#     #定义一个方法
#     def getName(self):
#         print("Hello",self.name)
# #类的引用
# print(People.name)
# #类的实例化
# p=People()
# print(p.name)")


# #异常
# try:
#     print(1/0)
# except ZeroDivisionError:
#     print("被除数为0")

# try:
#     x=int(input("Enter the first number:"))
#     y=int(input("Enter the second number:"))
#     print (x/y)
# except ZeroDivisionError:
#     print("被除数为0")

# a="abc"
# print(1/a)
# TypeError

# try:
#     x=int(input("Enter the first number:"))
#     y=int(input("Enter the second number:"))
#     print (x/y)
# except ZeroDivisionError:
#     print("被除数为0")
# except ValueError:
#     print("被除数不是数字")


# try:
#     x=int(input("Enter the first number:"))
#     y=int(input("Enter the second number:"))
#     print (x/y)
# except (ZeroDivisionError,ValueError):
#     print("被除数不合法")

# try:
#     x=int(input("Enter the first number:"))
#     y=int(input("Enter the second number:"))
#     print (x/y)
# except :
#     print("被除数不合法")

# try:
#     x=int(input("Enter the first number:"))
#     y=int(input("Enter the second number:"))
#     print (x/y)
# except ValueError as e: #e输出异常的错误名称
#     print("被除数不合法")
#     print(e) 

# try:
#     x=int(input("Enter the first number:"))
#     y=int(input("Enter the second number:"))
#     print (x/y)
# except ZeroDivisionError:
#     print("被除数为0")
# except ValueError as e:
#     print("被除数不是数字")
# else :
#     print("运行结果正确！")

# while True:
#     try:
#         x=int(input("Enter the first number:"))
#         y=int(input("Enter the second number:"))
#         print (x/y)
#     except ZeroDivisionError:
#         print("被除数为0")
#     except ValueError as e:
#         print("被除数不是数字")
#     else :
#         print("运行结果正确！")


# while True:
#     try:
#         x=int(input("Enter the first number:"))
#         y=int(input("Enter the second number:"))
#         print (x/y)
#     except ZeroDivisionError:
#         print("被除数为0")
#     except ValueError as e:
#         print("被除数不是数字")
#     else :
#         print("运行结果正确！")
#         break
#     finally:
#         print("this is finally!")



# def divide(x,y):
#     try:
#         result=x/y
#     except ZeroDivisionError:
#         print("被除数为0")
#     except Exception as e:
#         print(e)
#     else :
#         print("运行结果正确！",result)
#     finally:
#         print("this is finally!")
# print(divide(2,1))
# print(divide(2,0))
# print(divide(2,"a"))


# def fautly():
#     raise Exception("something is wrong")
# def ignore_exception():
#     fautly()
# def handle_exception():
#     try:
#         fautly()
#     except Exception as e:
#         print(e)
# # print(fautly())
# # print(ignore_exception())
# print(handle_exception())


# def infoPerson(person):
#     print("info of :",person["name"])
#     print("age:",person["age"])
#     # if "sex" in person:
#     #     print("sex:",person["sex"])
#     # else:
#     #     print("the sex is not exist")
#     try:  #if else 与 try except 功能效率都差不多 但是后者效率更高点 但是日常还是前者用的比较多
#         print("sex:"+person["sex"])
#     except KeyError:
#         pass
# dicts={"name":"bela","age":42,"sex":"boy"}
# infoPerson(dicts)

#自定义异常：继承exception
#自定义异常必须使用raise引发，而且只用通过手工方式触发
# class DivisonException(Exception):
#     def __init__(self,x,y):
#         Exception.__init__(self)
#         self.x=x
#         self.y=y
# try:
#     x=2
#     y=2
#     if x/y >0:
#         print(x/y)
#         raise DivisonException(x,y)
# except DivisonException as div:
#     print("DivisonException x/y=%.2f"%(div.x/div.y))
```
 目前都被注释掉

   
  