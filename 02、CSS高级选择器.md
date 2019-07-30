---
title: 02、CSS高级选择器
date: 2018-06-05 14:27:06
tags: CSDN迁移
---
  **first-of-type**   
 p:first-of-type 选择属性其父元素的首个p元素   
 **last-of-type**   
 p:last-of-type 选择属性其父元素的最后p元素   
 **only-of-type**   
 p:only-of-type 选择属于其父元素唯一的p元素   
 **first-child**   
 p:first-child选择属性其父元素的第一个子元素的p元素 该效果与first-of-type一样   
 **last-child**   
 p:last-child选择属性其父元素的最后一个子元素的p元素 该效果与last-of-type一样   
 **nth-child(n)**   
 p:nth-child(n)选择属性其元素的第n个子元素的p元素   
 **:before**   
 p:before在每个p元素的内容之前插入内容   
 **:after**   
 p:after在每个p元素的内容之后插入内容

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
/*        p:first-of-type{
            background: red;
        }
        p:last-of-type{
            background: green;
        }
        p:nth-child(2){
            background: blue;
        }*/
/*        p:only-of-type{
            background: pink;
        }*/
        p:first-child{
            background: #0f0;
        }
        p:last-child{
            background: gold;
        }
        p:nth-child(2):before{
            content: "你好,";
            color:wheat;
        }
        p:nth-child(3):after{
            content: "，再见！";
            color:yellow;
        }
    </style>
</head>
<body>
    <p>我是第一个元素</p>
    <p>我是第二个元素</p>
    <p>我是第三个元素</p>
    <p>我是第四个元素</p>
    <p>我是第五个元素</p>
    <p>我是第六个元素</p>
    <p>我是第七个元素</p>
<!--     <div><p>我是唯一的p元素</p></div>
    <div><p>我是p元素</p><p>我也是p元素</p></div> -->
</body>
</html>
```
 优先级算法   
 1、优先级就近原则，同样权重情况下，定义最近者优先

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        .myp{
            color: red
        }
        .myp{
            color: blue
        }
    </style>
</head>
<body>
  <p class="myp" id="myp">我是P标签</p>  
</body>
</html>
```
 最后的效果显示的是蓝色

 2、载入样式一最后载入的定位为准

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <link rel="stylesheet" href="stytle2.css">
    <link rel="stylesheet" href="stytle1.css">
    <style>
/*        .myp{
            color: red
        }
        .myp{
            color: blue
        }*/
    </style>
</head>
<body>
  <p class="myp" id="myp">我是P标签</p>  
</body>
</html>
```
 stytle1.css

 
```
p{
    color: pink;
}
```
 stytle2.css

 
```
p{
    color: yellow;
}
```
 最后的效果是 黄色

 3、！important>id>class>tag

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
<!--     <link rel="stylesheet" href="stytle2.css">
    <link rel="stylesheet" href="stytle1.css"> -->
    <style>
/*        .myp{
            color: red
        }
        .myp{
            color: blue
        }*/
        p{
            color: red
            !important
        }
        #myp{
            color: green
        }
        .p{
            color: blue
        }
    </style>
</head>
<body>
  <p class="myp" id="myp">我是P标签</p>  
</body>
</html>
```
 4 !important比内联优先级高，但内联比id更高

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
<!--     <link rel="stylesheet" href="stytle2.css">
    <link rel="stylesheet" href="stytle1.css"> -->
    <style>
/*        .myp{
            color: red
        }
        .myp{
            color: blue
        }*/
        p{
            color: red
            !important
        }
        #myp{
            color: green
        }/*
        .p{
            color: blue
        }*/
    </style>
</head>
<body>
  <p class="myp" id="myp" style="color: lightgreen">我是P标签</p>  
</body>
</html>
```
 最后是红色

   
  