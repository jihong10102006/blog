---
title: 02、html基础学习笔记二---表格和表单
date: 2018-05-29 15:24:13
tags: CSDN迁移
---
  ```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">

    </head>
    <body>
        <!--table：表标签 ；caption：表标题；tr:行标签；td:列标签；th:列标题-->
        <table border="1" width="800" height="100" bgcolor="aliceblue" >
            <caption><h2>成绩单案例</h1></caption>
            <tr bgcolor="azure" >
                <th>姓名</th>
                <th>科目</th>
                <th>成绩</th>
            </tr>
            <tr align="center">
                <td>小花</td>
                <td>Java</td>
                <td>85</td>
            </tr>
            <tr align="center">
                <td>小李</td>
                <td>html</td>
                <td>90</td>
            </tr>
            <tr align="center">
                <td>小红</td>
                <td>IOS</td>
                <td>98</td>
            </tr>
        </table>
        </br>
        </br>

        <!--colspan类似合并列单元格；rowspan合并行单元格-->
        <table border="1">
            <caption>通讯录</caption>
            <tr align="center" bgcolor="#CCCCCC">
                <td>姓名</td>
                <td colspan="2">编码</td>
            </tr>
            <tr>
                <td>liba</td>
                <td>123456</td>
                <td>789101</td>
            </tr>
            <tr>
                <td>mary</td>
                <td>987650</td>
                <td>345897</td>
            </tr>
        </table>
        </br>
        </br>
        </br>

        <!--form:表单标签 ；name：名称 ；action：服务器程序的url;method：提交信息方式-->
        <!--属性type：指定表单元素的类型；name：指定表单元素的名称；value：指定表单元素的初始值：size:指定表单元素的初始宽度-->
        <form>
            用户：<input type="text" name="username" /><br />
            密码：<input type="password" name="pwd" /><br />
            性别：<input type="radio" name="gender" value="男" />男
                 <input type="radio" name="gender" value="男" />女<br />
            爱好：<input type="checkbox" name="hobby"  value="读书"/>    读书 
                 <input type="checkbox" name="hobby"  value="游戏"/>  游戏 
                 <input type="checkbox" name="hobby"  value="电影"/>  电影 <br />
            城市：<select>
                    <option value="北京">北京</option>
                    <option value="上海">上海</option>
                    <option value="深圳">深圳</option>              
                </select>
                <br />
            自我介绍：<textarea cols="20" rows="10">
                    请自己我介绍一下
                  </textarea>
                  <br />
            照片：<input type="file" name="fileImg" /><br />
            <input type="button"  name="btn" value="注册"/>
            <input type="reset"  name="btn" value="取消"/>
        </form>
    </body>
</html>

```
   
  