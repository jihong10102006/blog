---
title: 11、Div+CSS基础笔记---子容器相对于父容器的绝对定位
date: 2018-05-31 16:15:38
tags: CSDN迁移
---
  ```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <style>
            #father{
                width: 400px;
                height: 300px;
                background-color: lightcyan;
                position: absolute;/*父容器绝对定位*/
                left: 50px;
                top: 50px;
                }
            #son1,#son2,#son3{width: 100%;height: 60px;margin-top: 5px;background-color: hotpink;}
            #son3{position: absolute;right: 50px;top: 150px;width:60px;background-color: royalblue;}
        </style>
    </head>
    <body>
        <div id="father">
            <div id="son1">子容器1</div>
            <div id="son2">子容器2</div>
            <div id="son3">子容器3</div>
        </div>
    </body>
</html>

```
   
  