---
title: 09、Div+CSS基础笔记---盒子的水平间距、垂直间距
date: 2018-05-31 14:49:26
tags: CSDN迁移
---
  ```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <style>
            span{border: 1px solid #8A2BE2;padding: 10px 5px;}
            /*盒子的水平间距=左盒子的居右+右盒子的居左*/
            span#left{margin-right: 10px ;}
            span#right{margin-left: 30px;}

            div{border: 1px solid #FF0000;width: 100px;height: 50px;}
            /*盒子的垂直间距=为两者（上盒子的居底和下盒子的居顶）之间的最大值，即40px*/
            div#top{margin-bottom: 10px;}
            div#bottom{margin-top: 40px;}

        </style>
    </head>
    <body>
        <span id="left">左盒子</span>
        <span id="right">右盒子</span>
        </br></br></br><hr />

        <div id="top">上盒子</div>
        <div id="bottom">下盒子</div>


    </body>
</html>

```
   
  