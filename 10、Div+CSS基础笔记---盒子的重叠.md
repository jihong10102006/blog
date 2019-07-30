---
title: 10、Div+CSS基础笔记---盒子的重叠
date: 2018-05-31 15:08:39
tags: CSDN迁移
---
  ```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <style>
            div{ 
                position: absolute;/*设置盒子的绝对定位*/
                border: 1px solid #FF0000;
                width: 100px;
                height: 50px;
                }
            /*盒子的垂直间距=为两者（上盒子的居底和下盒子的居顶）之间的最大值，即40px*/
            div#top{margin-bottom: 10px;
            background-color:red;
            z-index: 10;/*将网页从Z轴方向，设置一个值，值越大,则被层叠在最上面*/
            }
            div#bottom{margin-top: 30px; 
            border: 1px solid green; 
            background-color: cyan;

            }

        </style>
    </head>
    <body>

        <div id="top">上盒子</div>
        <div id="bottom">下盒子</div>


    </body>
</html>

```
   
  