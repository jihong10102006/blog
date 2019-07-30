---
title: 03、HTML5新增input类型
date: 2018-06-05 17:06:39
tags: CSDN迁移
---
  类型           | 说明                        
     ------------ | -------------------------- 
     email        | 电子邮件地址文本框，提交表单时会自动验证email值
     url          | 网页的URL，提交表单时会自动验证URL值     
     color        | 主要用于选取颜色                  
     search       | 用于搜索引擎（搜索框）               
     number       | 只包含数值的字段，能够设定对所接受的数字的限制   
     range        | 滑动条，特定值范围内的数值选择器          
     Date pickers | 拥有多个可供选取日期的新输入类型          

 number

 
     属性    | 值      | 说明        
     ----- | ------ | ---------- 
     max   | number | 规定允许的最大值  
     min   | number | 规定允许的最小值  
     setp  | number | 规定合法对的数字间隔
     value | number | 规定的默认值    

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
   <form action="">
       <p>
           <input type="email">
           <input type="submit">
       </p>
       <p>
           <input type="url">
           <input type="submit">
       </p>
       <p>
           <input type="color">
       </p>
       <p>
           <input type="search">
           <input type="submit">
       </p>
       <p>
           <input type="number" max="10" min="2" step="2" value="3">
       </p>
       <p>
           <input type="range" max="50" min="10" step="3" value="10">
       </p>
       <p>
           <input type="date">           
       </p>
       <p>
           <input type="month">
       </p>
       <p>
           <input type="week">
       </p>
       <p>
           <input type="time">
       </p>
       <p>
           <input type="datetime">
       </p>
       <p>
           <input type="datetime-local">
       </p>
   </form> 
</body>
</html>
```
 效果图：   
 ![这里写图片描述](https://img-blog.csdn.net/20180605170609649?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

   
  