---
title: 05、CSS3基础----border-radius属性、box-shadow属性、background-size属性等
date: 2018-06-11 15:21:20
tags: CSDN迁移
---
  ```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        img{
            height: 200px;
            width:200px;
        }
        img:first-child{
            border-radius: 50%
        }
        img:nth-child(2){
            border-radius: 20px 60px
        }
        img:nth-child(3){
            border-radius: 20px 60px 100px
        }
        img:last-child{
            border-radius: 20px 40px 80px 100px
        }
    </style>
</head>
<body>
    <img src="picture.jpg" alt="">
    <img src="picture.jpg" alt="">
    <img src="picture.jpg" alt="">
    <img src="picture.jpg" alt="">
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180606154851325?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        #box{
            width: 200px;
            height: 200px;
            background: red;
            margin:20px 20px;
            box-shadow: 10px 10px 3px yellow ; 
        }

    </style>
</head>
<body>
    <div id=box></div>
</body>
</html>
```
 黄色阴影你效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180608165737726?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        p{
            height: 30px;
            width: 100px;
            padding: 50px;
            border:1px solid red;
            margin: 10px;
            background: url(picture.jpg) no-repeat;
        }
        .img1{
            background-size: 50px 80px;
        }
        .img2{
            background-size: 50%;
        }
        .img3{
            background-size: cover; 
        }
        .img4{
            background-size: contain;
        }

    </style>
</head>
<body>
    <p class="img1"></p>
    <p class="img2"></p>
    <p class="img3"></p>
    <p class="img4"></p>
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180611101328402?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        p{
            background: url(picture2.jpg) repeat;
            width:100px;
            border:10px dashed #ccc;
            padding: 30px;
            color: red;
        }
        .img1{
            background-origin: content-box;
            background-clip: content-box;
        }
        .img2{
            background-origin: border-box;
            background-clip: border-box;
        }
        .img3{
            background-position: padding-box;
            background-clip: padding-box;
        }
    </style>
</head>
<body>
    <p class="img1">
        我是文本我是文本我是文本我是文本我是文本我是文本我是文本我是文本我是文本
    </p>
    <p class="img2">
        我是文本我是文本我是文本我是文本我是文本我是文本我是文本我是文本我是文本
    </p>
    <p class="img3">
        我是文本我是文本我是文本我是文本我是文本我是文本我是文本我是文本我是文本
    </p>
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180611142102844?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

   
  