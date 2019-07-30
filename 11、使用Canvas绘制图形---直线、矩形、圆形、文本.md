---
title: 11、使用Canvas绘制图形---直线、矩形、圆形、文本
date: 2018-06-16 20:54:42
tags: CSDN迁移
---
  创建步骤：   
 1、有canvas元素   
 2、使用ID获取到canvas元素，通过使用id获取canvas元素：document.getElementById()   
 3、创建canvas对象：getContext(“2d”)

 绘制直线、矩形

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
    </style>
</head>
<body>
    <!-- 第一步：创建canvas元素 -->
    <canvas id="cvs" width="800" height="900"></canvas>
</body>
</html>
<script>
    // 第二步：通过Id获取到canvas元素
    var cvs=document.getElementById("cvs");
    // 第三步：创建canvas对象
    var cxt=cvs.getContext("2d");
    // 绘制一条直线
    cxt.moveTo(100,60)//起点
    cxt.lineTo(300,60)//终点
    cxt.strokeStyle="red";//设置线条颜色
    cxt.lineWidth="5";//设置线条宽度
    cxt.stroke();//绘制路径
    // 绘制矩形
    cxt.strokeStyle="green";//描边矩形边框颜色为绿色
    cxt.lineWidth="2";
    cxt.strokeRect(0,80,200,100);//描边的矩形，只有边框
    cxt.fillStyle="blue";//填充矩形的颜色为蓝色
    cxt.fillRect(0,200,200,100);//填充矩形，有颜色填充，默认是黑色

    cxt.fillStyle="yellow";//填充矩形的颜色为蓝色
    cxt.fillRect(0,350,200,100);
    cxt.clearRect(10,370,100,50);//清除矩形区域
</script>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180616201546232?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 绘制圆形、绘制文本

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
    </style>
</head>
<body>
    <!-- 第一步：创建canvas元素 -->
    <canvas id="cvs" width="2000" height="4000"></canvas>
</body>
</html>
<script>
    // 第二步：通过Id获取到canvas元素
    var cvs=document.getElementById("cvs");
    // 第三步：创建canvas对象
    var cxt=cvs.getContext("2d");
    // 绘制一条直线
    // cxt.moveTo(100,60)//起点
    // cxt.lineTo(300,60)//终点
    // cxt.strokeStyle="red";//设置线条颜色
    // cxt.lineWidth="5";//设置线条宽度
    // cxt.stroke();//绘制路径
    // // 绘制矩形
    // cxt.strokeStyle="green";//描边矩形边框颜色为绿色
    // cxt.lineWidth="2";
    // cxt.strokeRect(0,80,200,100);//描边的矩形，只有边框
    // cxt.fillStyle="blue";//填充矩形的颜色为蓝色
    // cxt.fillRect(0,200,200,100);//填充矩形，有颜色填充，默认是黑色

    // cxt.fillStyle="yellow";//填充矩形的颜色为蓝色
    // cxt.fillRect(0,350,200,100);
    // cxt.clearRect(10,370,100,50);//清除矩形区域

    // 绘制圆形
    cxt.arc(800,300,150,0,Math.PI*2,false);//Math.PI代表180度
    cxt.stroke();

    //绘制文本文字    
    cxt.font="48px 微软雅黑" //设置字体样式
    cxt.fillText("hello world",600,500);//绘制实心文字
    cxt.font="60px 微软雅黑" 
    cxt.strokeText("hello world",900,500)//绘制空心文本

</script>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180616205156379?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

   
  