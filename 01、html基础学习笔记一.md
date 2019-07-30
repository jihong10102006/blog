---
title: 01、html基础学习笔记一
date: 2018-05-29 13:40:42
tags: CSDN迁移
---
  使用HBulider工具环境

 
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
    </head>
    <body>
        <a href="#bottom">回到底部</a></br> <!--这个是最下面的定义回到底部的描点-->
        <!--这是我的第一个HTML网页-->
        测试&nbsp;&nbsp;&nbsp;&nbsp;效果
        <!--&nbsp是一个空格-->

        <!--h1是标题-->
        <h1>一号标题</h1>
        <h2>二号标题</h2>
        <h3>三号标题</h3>
        <h4>四号标题</h4>
        <h5>五号标题</h5>
        <h6>六号标题</h6>

        <!--p是段落标签-->
        <p>我是一个段落</p>
        <p>我是段落二</p>

        <!--/br是换行标签-->
        我是四个段落</br>
        我是段落五</br>

        <!--center是居中标签-->
        <center>我是一个互联网从业者</center>

        <!--有序列表ol中嵌套li-->
        <ol>
            <li>冠军</li>
            <li>亚军</li>
            <li>季军</li>
        </ol>

        <!--无序列表ul中嵌套li-->
        <ul>
            <li>水浒传</li>
            <li>三国演义</li>
            <li>红楼梦</li>
            <li>西游记</li>
        </ul>

        <!--自定义列表dl中定义dt(标题)，dd(内容)-->
        <dl>
            <dt>格力空调</dt>
            <dd>价格：9888，中国制造，拂服务良好</dd>
            <dt>海尔空调</dt>
            <dd>价格：9999，售后良好</dd>
        </dl>

        <!--预定义标签 pre:即页面显示的和代码中写的排样是一致的-->
        <pre>
        <center>
        春晓
        唐.李白
        春眠不觉晓，处处闻啼鸟
        夜来风雨声，花落知多少</center>
        </pre>

        <!--字体样式-->
        <p><font color="red" face="楷体" size="5">处处闻啼鸟</font></p>

        <!--导入图片-->
        <img src="img/picture.jpg" width="110" height="110" title="小美女"/></br>

        <!--超链接标签a href是指向的链接地址-->
        <a href="https://www.csdn.net/">csdn.net网站</a></br>

        <!--锚点：可以快捷的链接到同一个文档  先创建锚点(所放的位置要在回到这个某个位置的上一行) 然后再链接锚点-->
        <a name="xiaomeinv"></a>
        <img src="img/picture.jpg" width="110" height="110" title="小美女"/></br>
        </br></br></br></br></br></br></br>
        </br></br></br></br></br></br></br>
        </br></br></br></br></br></br></br>
        </br></br></br></br></br></br></br>
        <a href="#xiaomeinv">小美女</a>

        <!--锚点回到底部-->
        <a name="bottom"></a>       

    </body>
</html>

```
   
  