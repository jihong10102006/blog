---
title: C#枚举类型的定义，说明和使用
date: 2012-11-13 16:44:46
tags: CSDN迁移
---
   # 



 
# []()1.枚举的技术定义：

  [性质] [修饰符] enum 标识符 [：基类型] {枚举列表}；

 

 
# []()2.常用举例：(用逗号隔开)

  **[csharp]** [ view plain](#)[copy](#)[print](#)[?](#)  
   
 
  1. **enum** Temperatures 
  2. { 
  3. SMALL, 
  4. LARGE = 5 
  5. }   
 
```
enum Temperatures
{
	SMALL,
	LARGE = 5
}
```
  
  
 **说明：**  
 1.基类型默认为int，但是可以任意使用ushort,long等，char除外。数据为常量，不可更改。上例和const int SMALL=0等价  
 2.要显示一个枚举常量的值，需将常量转换为它的底层类型。上面的例子应该转为int型。

 3.枚举中的每个常量都对应一个值。上面的例子是整数，如果不特别设置，枚举从0开始，后一个是前一个加1。上面的SMALL则为0，LARGE为5。

 4.枚举型和整数型之间的转换需要显式进行。

 5.C++中，限制对枚举型赋值整数，但是允许枚举提升(promote)为整数，以实现整数赋值。

 6.基类型包括：byte、sbyte、short、ushort、int、uint、long 和 ulong。  


 

 
# []()3.显示举例：

  

 **[csharp]** [ view plain](#)[copy](#)[print](#)[?](#)  
   
 
  1. System.Console.WriteLine("显示SMALL的值: {0}", (**int**)Temperatures.SMALL);   
   
 