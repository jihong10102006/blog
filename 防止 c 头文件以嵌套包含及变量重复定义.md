---
title: 防止 c 头文件以嵌套包含及变量重复定义
date: 2012-11-06 16:05:33
tags: CSDN迁移
---
   #include文件的一个不利之处在于一个头文件可能会被多次包含，为了说明这种错误，考虑下面的代码:

 #include "x.h"  
#include "x.h"  
  
显然，这里文件x.h被包含了两次，没有人会故意编写这样的代码。但是下面的代码:  
#include "a.h"  
#include "b.h"  
  
看上去没什么问题。如果a.h和b.h都包含了一个头文件x.h。那么x.h在此也同样被包含了两次，只不过它的形式不是那么明显而已。  
  
多重包含在绝大多数情况下出现在大型程序中，它往往需要使用很多头文件，因此要发现重复包含并不容易。要解决这个问题，我们可以使用条件编译。如果所有的头文件都像下面这样编写:  
#ifndef _HEADERNAME_H  
#define _HEADERNAME_H  
  
...//(头文件内容)  
  
#endif  
  
那么多重包含的危险就被消除了。当头文件第一次被包含时，它被正常处理，符号_HEADERNAME_H被定义为1。如果头文件被再次包含，通过条件编译，它的内容被忽略。符号_HEADERNAME_H按照被包含头文件的文件名进行取名，以避免由于其他头文件使用相同的符号而引起的冲突。  
  
 但是，你必须记住预处理器仍将整个头文件读入，即使这个头文件所有内容将被忽略。由于这种处理将托慢编译速度，所以如果可能，应该避免出现多重包含。

 test-1.0使用#ifndef只是防止了头文件被重复包含(其实本例中只有一个头件，不会存在重复包含的问题)，但是无法防止变量被重复定义。  
  
# vi test.c  
-------------------------------  
#include <stdio.h>  
#include "test.h"  
  
extern i;  
extern void test1();  
extern void test2();  
  
int main()  
{  
 test1();  
 printf("ok\n");  
 test2();  
 printf("%d\n",i);  
 return 0;  
}  
  
  
# vi test.h  
-------------------------------  
#ifndef _TEST_H_  
#define _TEST_H_  
  
char add1[] = "www.shellbox.cn\n";  
char add2[] = "www.scriptbox.cn\n";  
int i = 10;  
void test1();  
void test2();  
  
#endif  
  
  
  
# vi test1.c  
-------------------------------  
#include <stdio.h>  
#include "test.h"  
  
extern char add1[];  
  
void test1()  
{  
 printf(add1);  
}  
  
  
  
# vi test2.c  
-------------------------------  
#include <stdio.h>  
#include "test.h"  
  
extern char add2[];  
extern i;  
  
void test2()  
{  
 printf(add2);  
 for (; i > 0; i--)   
 printf("%d-", i);  
}  
  
  
  
# Makefile  
-------------------------------  
test: test.o test1.o test2.o  
test1.o: test1.c  
test2.o: test2.c  
clean:  
 rm test test.o test1.o test2.o  
  
  
错误:  
test-1.0编译后会出现"multiple definition of"错误。  
  
错误分析:  
由于工程中的每个.c文件都是独立的解释的，即使头文件有  
#ifndef _TEST_H_  
#define _TEST_H_  
....  
#enfif  
在其他文件中只要包含了global.h就会独立的解释,然后每个.c文件生成独立的标示符。在编译器链接时，就会将工程中所有的符号整合在一起，由于文件中有重名变量，于是就出现了重复定义的错误。  
  
解决方法  
在.c文件中声明变量，然后建一个头文件(.h文件)在所有的变量声明前加上extern，注意这里不要对变量进行的初始化。然后在其他需要使用全局变量的.c文件中包含.h文件。编译器会为.c生成目标文件，然后链接时，如果该.c文件使用了全局变量，链接器就会链接到此.c文件 。  
  
  
  
  
  
  
test-2.0  
  
# vi test.c  
-------------------------------  
#include <stdio.h>  
#include "test.h"  
  
int i = 10;  
char add1[] = "www.shellbox.cn\n";  
char add2[] = "www.scriptbox.cn\n";  
extern void test1();  
extern void test2();  
  
int main()  
{  
 test1();  
 printf("ok\n");  
 test2();  
 printf("%d\n",i);  
 return 0;  
}  
  
  
# vi test.h  
-------------------------------  
#ifndef _TEST_H_  
#define _TEST_H_  
  
extern i;  
extern char add1[];  
extern char add2[];  
  
void test1();  
void test2();  
  
#endif  
  
  
  
# vi test1.c  
-------------------------------  
#include <stdio.h>  
#include "test.h"  
  
void test1()  
{  
 printf(add1);  
}  
  
  
# vi test2.c  
-------------------------------  
#include <stdio.h>  
#include "test.h"  
  
void test2()  
{  
 printf(add2);  
 for (; i > 0; i--)   
 printf("%d-", i);  
 }  
  


   
 