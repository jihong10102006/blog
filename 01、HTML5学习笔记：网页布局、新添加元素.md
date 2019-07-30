---
title: 01、HTML5学习笔记：网页布局、新添加元素
date: 2018-06-04 16:10:03
tags: CSDN迁移
---
  **HTML5的应用场景：**   
 酷炫网站制作、游戏开发、移动开发、应用开发   
 **HTML5新添结构元素：**   
 header：页面或页面中某一个区块的页眉，通常是一些引导和导航   
 nav：可以作为页面导航的链接组   
 section：页面中的一个内容区块，通常由内容及其标题组成   
 article：代表一个独立的、完整的相关内容块，可独立页面其他内容适用   
 aside：非正文的内容，与页面的主要内容是分开的，被删除而不会影响到网页的内容   
 footer：页面或页面中某一区块的脚注

 使用工具:sublime   
 网页布局案例：

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        *{
            padding:0;
            margin: 0;
        }
        .box{
            width: 500px;
            height: 600px;
            border: 1px #ccc solid;
            margin: 30px auto;
        }
        .header{
            width: 500px;
            height: 40px;
            text-align: center;
            line-height: 40px;
            background: pink;
        }
        .main{
            width: 500px;
            height: 520px;
        }
        .footer{
            width: 500px;
            height: 40px;
            text-align: center;
            line-height: 40px;
            background: pink;
        }
        .nav{
            width: 500px;
            height: 30px;
            line-height: 30px;
            background: lightgreen;
        }
        .container{
            width: 500px;
            height: 490px;
        }
        .aside{
            width: 150px;
            height: 490px;
            float: left;
            background: skyblue;
            text-align: center;
            line-height:490px;
        }
        .article{
            width: 350px;
            height: 490px;
            float: left;
            text-align: center;
            background: yellow;
            line-height: 490px;
        }
    </style>
</head>
<body>
    <div class="box">
        <header class="header">头部</header>
        <main class="main">
            <nav class="nav">导航</nav>
            <div class="container">
                <aside class="aside">侧边栏</aside>
                <article class="article"></article>
            </div>
        </main>
        <footer class="footer">底部</footer>
    </div>
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180604141912377?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 video：定义视频，如电影片段或其他视频流   
 audio：定义音频，如音乐或其他音频流   
 canvas：定义图形   
 datalist：定义可选数据的列表   
 time：标签定义日期或时间   
 mark：在视觉上向用户呈现那些需要突出的文字   
 网页元素：

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <h4>可选数据列表</h4>
    <input list="city">
    <datalist id="city">
        <option value="北京">北京</option>
        <option value="上海">上海</option>
        <option value="广州">广州</option>
        <option value="深圳">深圳</option>
        <option value="南京">南京</option>
        <option value="杭州">杭州</option>
    </datalist>
    <h4>时间标签</h4>
    <p>今天我<time>8:00</time>起床</p>
    <h4>mark标签</h4>
    <p><mark>CSDN</mark>，学院学习</p>
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180604145659178?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 新增全局属性   
 contentEditable：规定是否允许用户编辑内容   
 designMode：规定整个页面是否可编辑   
 hidden：规定对元素进行隐藏   
 spellcheck：规定是否必须对元素进行拼写或语法检查   
 tabindex：规定元素的tab键迭制次序

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <h4>contenteditable</h4>
    <p contenteditable="true">这个段落应该允许被编辑</p>
    <h4>designMode</h4>
     <p>这个段落应该允许被编辑</p>
     <p>这个段落应该允许被编辑</p>
     <p>这个段落应该允许被编辑</p>
     <h4>hidden</h4>
     <p hidden>这个段落应该被隐藏</p>
     <h4>spellcheck</h4>
     <p contenteditable="true" spellcheck="true">这个段落可以进行语法检查</p>
     <h4>tabindex</h4>
     <p><a href="" tabindex="2">我是第二个</a></p>
     <p><a href="" tabindex="1">我是第一个</a></p>
     <p><a href="" tabindex="3">我是第三个</a></p>
</body>
</html>
<script>
    //document.designMode="on";//可以被编辑
    document.designMode="off"://不可以被编辑
</script>
```
   
  