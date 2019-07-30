---
title: 03、html基础学习笔记三---CSS中三种选择器
date: 2018-05-30 09:59:28
tags: CSDN迁移
---
  CSS中三种选择器：标签选择器、类选择器、ID选择器

 
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>     
        <style>
            /*CSS层叠样式表：增强网页样式并将样式与内容分离的标签性语言。样式的规则都写在<style></s tyle>标签内部：由选择器、属性、属性值构成*/
            /*选择器有：标签选择器（使同类标签样式一致）、类选择器(想定义其中的某个标签为其他样式)、ID选择器(用法与class选择器基本相同，但在HTML页面中只能使用一次，一般用在划分网页时候)*/
            p{font-family: "微软雅黑";/*字体类型*/
            font-size: 24px;
            color: red; 
            text-align: center;/*字体对齐方式*/
            font-weight: bold;/*定义字体粗细*/
            }  /*标签选择器  应用于网页中一样的标签，如这里是p标签，则应用于所有p标签*/
            .author{font-size: 14px;color:#CCCCCC;font-style: italic;} /*类选择器 需在类名前加点号 单独应用于使用该类的标签 格式：class=""*/
            #timu{font-size: 30px;font-family: "粗体";color: green;text-align: center;}/*ID选择器 需在ID前加# 单独应用于使用该ID的标签 格式：id=""*/
            body{background-color: aqua; /*设置背景颜色*/
                background-image: url(img/picture.jpg);/*设置背景图片*/
                background-repeat: no-repeat;/*背景图像重复的方式*/
                background-position: top;/*背景图像的位置*/
                }
        </style>
    </head>
    <body>
        <h2 id="timu">静夜思</h2>
        <p class="author">作者:李白 唐朝大诗人</p>
        <p>床前明月光</p>
        <p>疑是地上霜</p>
        <p>举头望明月</p>
        <p>低头思故乡</p>
    </body>
</html>

```
   
  