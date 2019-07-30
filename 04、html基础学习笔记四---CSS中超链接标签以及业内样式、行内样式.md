---
title: 04、html基础学习笔记四---CSS中超链接标签以及业内样式、行内样式
date: 2018-05-30 10:34:53
tags: CSDN迁移
---
  ```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <style>
            table{width: 100%;border-collapse: collapse;text-align: center;}
            td{border: 1px solid #00f}
            a{text-decoration: none;} /*去除a标签的下划线样式*/
            a:hover{text-decoration: underline;/*a:hover代表的是鼠标经过时的超链接；*/
            color: yellow;
            background-color:darksalmon;
            }

        </style>
    </head>
    <body>
        <table>
            <tr style="background-color: lightblue;">
                <td><a href="#">首页</a></td>
                <td><a href="#">留言</a></td>
                <td><a href="#">日志</a></td>
                <td><a href="#">游戏</a></td>
                <td><a href="#">读书</a></td>
                <td><a href="#">军事</a></td>
                <td><a href="#">新闻</a></td>
            </tr>
        </table>
    </body>
</html>

```
   
  