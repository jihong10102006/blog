---
title: 12、Div+CSS基础笔记-----相对定位与绝对定位以及包含块的定位情况
date: 2018-05-31 17:17:21
tags: CSDN迁移
---
  ```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <style>
            #a,#b{width: 200px;
            height: 100px;
            border: 1px solid black;
            float: left;/*左浮动：靠左横排显示*/
            margin-top: 50px;
            }
            #a{position: absolute;  /*a容器绝对定位：移动位置后，原来的位置不会被保存，即会被别的元素占用*/
               margin-right: 50px;
               margin-top: 200px}
            #b{margin-left: 100px;
               position: relative;/*b容器是相对定位；即相对于原来所在的位置进行移动，虽然最后移动了，但是原来的位置会被保留不会被别的占用*/
               border: 1px solid fuchsia;
              }
            #c,#d{width: 50%;height: 50%;position: relative;left: 50%; }
            #c{background-color: darkseagreen;}
            #d{background-color: crimson;}
        </style>
    </head>
    <body>
        <div id="a">
            <div id="c">c</div>
        </div>
        <div id="b">
            <div id="d">d</div>
        </div>
    </body>
</html>

```
 包含块的绝对定位或者相对定位，位置都不变，即 c和d的块位置分别相对于a和b的容器来说，不管是绝对定位还是相对定位，位置都不变

   
  