---
title: 13、HTML5本地存储
date: 2018-06-19 14:20:48
tags: CSDN迁移
---
  Cookie 存储页面上的用户名、密码、记录时间等   
 **Cookie**特性：   
 -同一个网站中的所有页面共享一套cookie(如：IE上存储了，Google上没存储)   
 -数量、大小有限（大小4KB）   
 -过期时间（**存储时间可以自己设置**）   
 -cookie是随HTTP事务一起被发送给服务器

 本地存储   
 本地存储（web storage），就是在Web上存储数据，而这里的存储时针对客户端本地而言的   
 web storage分为两类：   
 sessionStorage   
 localStorage   
 本地存储特点：   
 -存储量限制(5M)   
 -客户端完成，不会请求服务器处理   
 -sessionStorage 数据时不共享、localStorage共享   
 **sessionStorage**   
 session临时回话，从**页面打开到页面关闭的时间段**   
 窗口的临时存储、页面关闭，本地存储消失   
 **localStorage**   
 **永久存储**（可以手动删除数据）

 web storage本地存储的常用方法   
 setItem() 设置数据，key\value类型，类型都是字符串   
 getItem()获取数据，通过 key来获取到相应的value   
 removeItem()删除数据，通过key来删除相应的value

 以下代码是使用webstorm工具运行的（因为webstorm是自带服务器的）   
 webstorm工具下载地址：[https://download.csdn.net/download/jihong10102006/10486507](https://download.csdn.net/download/jihong10102006/10486507)

 
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        input{
            margin: 5px;
        }
    </style>
</head>
<body>
    <input type="text"/><br/>
    <input type="button" value="存储数据"/>
    <input type="button" value="获取数据"/>
    <input type="button" value="删除数据"/>
</body>
</html>
<script>
    //获取所有input元素
    var inputs=document.getElementsByTagName("input");
    inputs[1].οnclick=function () {
        // inputs[0].value获取第一个文本框输入的值
       // window.sessionStorage.setItem("name1",inputs[0].value);
        window.localStorage.setItem("name2",inputs[0].value);
    }
    inputs[2].οnclick=function(){
       // alert(window.sessionStorage.getItem("name1"));
        alert(window.localStorage.getItem("name2"));
    }
    inputs[3].οnclick=function(){
        inputs[0].value=" ";
      //  window.sessionStorage.removeItem("name1");
        window.localStorage.removeItem("name2");
    }
</script>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180619141955394?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

   
  