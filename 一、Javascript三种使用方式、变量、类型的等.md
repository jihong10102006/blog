---
title: 一、Javascript三种使用方式、变量、类型的等
date: 2018-07-11 11:17:13
tags: CSDN迁移
---
  **JavaScript可进行**   
 1）表单验证——减轻服务器压力   
 2）制作页面特效   
 3）动态改变页面内容   
 **JavaScript**是一种基于对象和事件驱动的脚本语言   
 **JavaScript特点：**   
 - 交互、运行在客户端的脚本语言、解释性语言   
 - 边执行边解释   
 - 跨平台   
 **JavaScript组成**   
 ![这里写图片描述](https://img-blog.csdn.net/2018070920070486?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)   
 ECMAScript是一种语法标准：语法、变量和数据类型、运算符、逻辑控制语句、关键字、保留字、对象   
 BOM：Browser Object Model（浏览器对象模型）提供了独立于内容与浏览器窗口进行交互的对象   
 简单理解：就是JavaScript与浏览器进行的交互

 DOM：Document Object Model（文档对象模型）是HTML文档对象模型（HTML DOM）定义的一套标准方法，用来访问和操纵HTML文档   
 简单理解：每个网页打开都被加载成HTML文档，操作网页里面的内容就是 DOM

 **Javascript的基本结构**   
 javascript在网页中应用有三种：   
 1）、直接使用 

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script type="text/javascript">
        // js内嵌式使用
        document.write("hello js!");
        document.write("<br><h1>hello 脚本语言！</h1>")
    </script>
</head>
<body>

</body>
</html>
```
 2）外部JS文件（有乱码出现：因为HTML是UTF-8模式，JS是GBK或者GB132 ；解决办法：webstorm工具中—file—setting—file encoding—project encoding 改成uft-8 ；或者直接在script 中加入charset=”utf-8”）

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>js外链式使用</title>    
    <script src="text.js"></script>
</head>
<body>
</body>
</html>
```
 text.js:

 
```
document.write("hello js!");
document.write("<br><h1>hello 脚本语言！</h1>")
```
 3）直接在HTML标签中使用

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>js在标签中的使用</title>
</head>
<body>
<input type="button"value="点我" onclick="javasript:alert('hello')">
</body>
</html>
```
 其中第三种很少用，常用的是第一、第二种，其中第二种最常用

 **JavaScript的执行原理**   
 ![这里写图片描述](https://img-blog.csdn.net/20180709211603555?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 **变量类型及变量**

 **变量**

 1）先声明变量在赋值   
 var width；   
 width=10；

 2）同时声明和赋值变量   
 var userName=“六月”   
 var i,j,k=15;

 3）不声明直接赋值   
 userName=“六月”   
 i=1；

 最后一种不建议使用

 **数据类型**   
 unddfined 未定义 如：变量声明未赋值   
 null 空值 用在对象上 ，空的对象   
 number 数值型   
 boolean 布尔型 true /false   
 string 字符串 用单引号或者双引号都可以   
 object 对象型

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>变量和数据类型</title>
</head>
<body>
<script>
    // 声明变量并使用;typeof判断数据类型
    var number1=10;
    document.write("number1的数据类型是："+typeof number1);
    var b;
    document.write("<br/>b的数据类型是："+typeof b);
    var c=undefined;
    document.write("<br/>c的数据类型是："+typeof c);
    var result=5>3;
    document.write("<br/>result："+ result);
    document.write("<br/>result的数据类型是："+typeof result);
    var str="hello";
    document.write("</br>str的数据类型是："+typeof str);
    var str2=null;
    document.write("</br>str2的数据类型是："+typeof str2);
</script>
</body>
</html>
```
 运行结果：   
 ![这里写图片描述](https://img-blog.csdn.net/20180709213900645?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 **运算符**

 ![这里写图片描述](https://img-blog.csdn.net/20180709214829935?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<script>
    var number1=9;
    var number2=4;
    document.write("number1="+number1+"     number2="+number2);
    // 商
    document.write("<br/> number1/number2 ="+(number1/number2));
    // 取余
    document.write("<br/> number1%number2 ="+(number1%number2));
    number1++;//自加
    document.write("<br/> number1:"+number1);
    number1--;//自减
    document.write("<br/> number1:"+number1);
    document.write("<br/> 结果:"+(number1==9));
    document.write("<br/> 结果:"+(number1!=9));
</script>
</body>
</html>
```
 运行结果：   
 ![这里写图片描述](https://img-blog.csdn.net/20180709221114259?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 **选择结构**

   
  