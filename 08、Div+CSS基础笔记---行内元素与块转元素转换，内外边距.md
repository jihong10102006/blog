---
title: 08、Div+CSS基础笔记---行内元素与块转元素转换，内外边距
date: 2018-05-31 11:19:25
tags: CSDN迁移
---
  ```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <style>
            div{border: 1px solid #FF0000;}
            #head{height: 20px;}
            #daohang{height: 300px;}
            #daohang2{height: 400px;}
            #footer{height: 30px;}          
            /*块状标签默认独占一行：宽100%，可以设置宽高；
             行内标签设置宽高无效*/
            .firstLetter{
                color: green;
                font-size: 3em; /*字体是默认字体的3倍*/
                float: left; /*产生下沉效果*/
            }
            /*将行内元素转换成块状元素;  display:inline 行内显示，none 隐藏，block 块状显示
            a{display: block; 
              height: 40px;
              width: 100px;
              background-color:blueviolet;

            }*/

            #menu li{list-style: none;
            width: 100px;
            height: 20px;
            background-color: cornflowerblue;
            float: left;
            margin: 5px; /*外边距*/
            text-align: center;
            padding: 10px 0; /*内边距*/
            }

        </style>
    </head>
    <body>
        <div id="head">头部</div>
        <div id="daohang">
            <a href="#">新闻</a>
            <a href="#">地理</a>
            <a href="#">自然</a>
            <a href="#">军事</a>
            <a href="#">娱乐</a>
            <a href="#">科技</a>
        </div>
        <div id="daohang2">
            <ul id="menu">
                <li><a href="#">新闻2</a></li>
                <li><a href="#">地理2</a></li>
                <li><a href="#">自然2</a></li>
                <li><a href="#">军事2</a></li>
                <li><a href="#">娱乐2</a></li>
                <li><a href="#">科技2</a></li>
            </ul>
        </div>
        <div>
            <h1>W3C</h1>
            <hr />
            <p><span class="firstLetter">w3c</span>是万维网的缩写万维网联盟创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构。万维网联盟创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构。到目前为止，W3C已发布了200多项影响深远的Web技术标准及实施指南，万维网联盟创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构。到目前为止，W3C已发布了200多项影响深远的Web技术标准及实施指南，到目前为止，W3C已发布了200多项影响深远的Web技术标准及实施指南，创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构。万维网联盟创建于1994年，是Web技术领域最具权威和影响创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构。万维网联盟创建于1994年，是Web技术领域最具权威和影响创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构。万维网联盟创建于1994年，是Web技术领域最具权威和影响创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构。万维网联盟创建于1994年，是Web技术领域最具权威和影响创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构。万维网联盟创建于1994年，是Web技术领域最具权威和影响创建于1994年，是Web技术领域最具权威和影响力的国际中立性技术标准机构。万维网联盟创建于1994年，是Web技术领域最具权威和影响</p>
        </div>
        <div id="footer">脚部</div>
    </body>
</html>

```
   
  