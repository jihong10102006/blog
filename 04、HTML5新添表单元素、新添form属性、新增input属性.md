---
title: 04、HTML5新添表单元素、新添form属性、新增input属性
date: 2018-06-06 15:25:48
tags: CSDN迁移
---
  元素     | 说明         
     ------ | ----------- 
     output | 标签定义不同类型的输出

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <!-- oninput 触发事件输出，parseInt（）转换成整型-->
    <form action="" oninput="x.value=parseInt(a.value)+parseInt(b.value)">
        <input type="range" id="a">+
        <input type="number" id="b">=
        <output id="x"></output>
    </form>
</body>
</html>
```
 效果图如下：   
 ![这里写图片描述](https://img-blog.csdn.net/20180606143814269?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 新添form属性

 
     属性           | 说明                                 
     ------------ | ----------------------------------- 
     autocomplete | form或input域名自动完功能：即记得之间输入的内容，能在下面提示
     novalidate   | 提交表单时不验证form或者input域               

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <form action="demo.php" autocomplete="off" novalidate>
        <p>用户名：<input type="text" name="name1"></p>
        <p>邮箱：<input type="email" name="name2"></p>
        <p><input type="submit"></p>
    </form>
</body>
</html>
```
 新增input属性

 
     属性           | 说明                         
     ------------ | --------------------------- 
     autofocus    | 页面加载时自动获得焦点                
     required     | 规定输入域不能为空                  
     placeholder  | 提供一种提示，描述输入域所期待的值          
     pattern      | 规定验证input域的模式（正则表达式）       
     height、width | 仅适用于image类型的input标签的图像高度和宽度

 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <form action="demo.php" autocomplete="off" >
        <p>用户名：<input type="text" name="name1" autofocus></p>
        <p>邮箱：<input type="email" name="name2" required></p>
        <p>邮箱：<input type="email" name="name3" placeholder="不能缺少@符号"></p>
        <p>描述：<input type="text" pattern="[a-zA-Z]{3}"></p>
        <p><input type="submit"></p>
        <p>
            <input type="image" src="picture.jpg" width="100" height="100">
        </p>
    </form>
</body>
</html>
```
   
  