---
title: 06、CSS3基础----CSS3渐变、文字效果、CSS3字体
date: 2018-06-11 17:16:27
tags: CSDN迁移
---
  ```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        div{
            height: 200px;
            margin-top: 10px;
        }
        #box1{
            background: linear-gradient(to bottom,red,blue)
        }
        #box2{
            background: linear-gradient(to left,red,green)
        }
        #box3{
            width:200px;
            background: linear-gradient(to bottom right,yellow,blue)
        }
        #box4{
            background: linear-gradient(to right,red,orange,yellow,green,cyan,blue,purple)
        }
        #box5{            
            background: radial-gradient(red,yellow,blue)
        }
        #box6{            
            background: radial-gradient(red 5%,yellow 20%,blue 75%)
        }
        #box7{ 
            width: 200px;           
            background: radial-gradient(circle,red,yellow,blue)
        }
    </style>
</head>
<body>
    <!-- 从上到下的线性渐进 -->
    <div id="box1"></div>
    <!-- 从右到左的渐变 -->
    <div id="box2"></div>
    <!-- 从左上角到右下角 -->
    <div id="box3"></div>
    <!-- 彩虹渐变 -->
    <div id="box4"></div>
    <!-- 径像渐变 -->
    <div id="box5"></div>
    <div id="box6"></div>
    <div id="box7"></div>
</body>
</html>
```
 ![这里写图片描述](https://img-blog.csdn.net/2018061115542482?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        h1{
            text-shadow: 5px 5px 5px red;
        }
        p{
            width: 200px;
            border:1px solid red;
            word-wrap: break-word;/*允许长单词换行*/
        }
        h2{
            width: 200px;
            border:1px solid pink;
            white-space: nowrap; /*文本不会换行，在同一行继续*/
            overflow: hidden;/*溢出隐藏*/
            text-overflow: ellipsis;/*用省略号来代表被修剪的文本*/
        }
    </style>
</head>
<body>
    <h1>Hello,text-shadow</h1>
    <p>this is a longlonglonglongonglonglonglongonglonglonglongw text</p>
    <h2>快到端午节，天气也热了！</h2>
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180611161833763?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        @font-face{
            font-family: myfont;
            src:url(C:/Windows/Fonts/Gabriola.ttf);
            font-weight: normal;
            font-style: normal;
        }
        h1{
           font-family: myfont;
            font-size: 30px;
        }
    </style>
</head>
<body>
    <h1>This is a long text</h1>
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/2018061117111186?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 总结：   
 设置网页元素边框：圆角、图片、阴影   
 设置网页元素背景：尺寸、定位/绘制区域、渐变   
 设置文本效果：阴影、换行、省略号   
 自定义网页字体：@font-face

   
  