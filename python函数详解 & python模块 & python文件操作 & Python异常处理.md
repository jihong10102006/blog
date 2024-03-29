---
title: python函数详解 & python模块 & python文件操作 & Python异常处理
date: 2019-06-06 18:52:31
tags: CSDN迁移
---
  ## []()Python函数

 **Python函数**  
 Python函数的本质：功能的封装。可以提高编程效率与程序的可读性。

 **局部变量与全局变量**  
 变量是有生效范围的，这个生效的范围就是作用域。  
 作用域从变量出现开始到程序最末，该变量是全局变量。  
 作用域只在局部的变量叫做局部变量  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190605154920367.png)  
 **函数的定义与调用**  
 函数定义的格式：  
 def 函数名(参数)：  
         函数体  
 函数调用格式：  
 函数名（参数）  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2019060516043220.png)  
 **函数参数使用**  
 给函数加入一些参数，参数的作用：与外界沟通的接口  
 形参：占地方，不起作用，一般用在函数定义的时候  
 实参：一般用在函数调用时候  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190605182934805.png)

 
## []()python模块

 为了让Python程序实现起来方便，可以按需求类别将一些常见的功能（函数）组合在一起，形成模块。若以后需要实现这一功能，可以直接导入对应的模块。简而言之：程序段与程序段组成了函数，函数与函数组成了模块。模块里面的函数称为模块的方法。  
 系统自带的模块在安装目录的lib目录中  
 找模块可以在lib中找，也可在lib下的site-packages中找

 **Python模块的导入两种方式**：

  
  * import 模块名  
     导入的是该模块里面的所有方法
    
      
  * from 模块名 import 方法  
     导入的是该模块下的某个方法
    
       比如：导入lib下的cgi.py模块  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190606154837365.png)  
 **模块的类别**

 从来源分为：  
 1、自带模块：安装好Python后，lib目录下和site-packages目录下中的模块  
 2、第三方模块：别人写好的模块，一般是开源的，可以直接安装到系统，安装好后可使用  
 3、自定义模块：自己写的模块

 **第三方模块的安装**  
 安装方式有：  
 1、pip方式（网络安装）：通过命令行cmd进入命令界面，输入pip命令，回车 ，然后通过格式：pip install 模块名 进行安装。pip方式的安装要求网络环境必须畅通，否则会出现延迟，导致安装不成功。  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2019060616155175.png)![在这里插入图片描述](https://img-blog.csdnimg.cn/20190606161654261.png)2、whl下载安装的方式（下载安装）：在百度引擎中输入lfd Python 进入https://www.lfd.uci.edu/~gohlke/pythonlibs/。先下载后安装  
 假如选一个模块：Dipy  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190606162843837.png)  
 该模块下载完后，假如放入到地址：D:\python爬虫 ，然后通过cmd 命令进入命令行界面，首先进入该模块所放的目录：D:\python爬虫 ，然后通过格式： pip install 模块名全称 进行安装  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190606163624675.png)3、直接复制的方式：Python版本对应，电脑版本对应，有人安装好所需模块，可以直接复制到自己电脑中的对应文件中。  
 4、anaconda

 **自定义模块使用**  
 只要把编写的Python文件放到lib目录下，该文件成为一个模块  
 编写一个名为mymd的Python模块，并放在lib目录下，然后Python shell来进行导入调用  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190606165033317.png)

 
## []()Python文件操作

 **文件操作概**  
 Python程序对可以对文件进行打开、关闭、读取、写入等操作，使用Python进行文件操作可以自动对程序进行处理，比如合并多个Excel表格文件的内容等。  
 打开格式：open(文件地址,操作形式)

  
  * w:写入 
  * r:读取 
  * b:二进制 
  * a:追加，是指在文件的末尾追加写入  **文件的读取**  
 文件读取得前提需要打开文件，打开文件的前提是该文件存在，假如在目录D:\python爬虫中放入文本1.txt的文档，并写入信息保存。  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2019060617425837.png)打开文本1.txt地址：D:\python爬虫\文本1.txt ，需要对里面的 \ 进行转义，把 \ 换成双斜杠或者换成 /  
 read() ：读取所有的内容  
 readline(）：读取一行内容

 **文件的关闭**  
 文件打开后必须关闭，若不关闭，造成后续程序出错  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190606181754843.png)  
 **文件写入**  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190606184449860.png)  
 只有在close()后，才会保存文本中的内容  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190606184702213.png)  
 再次写入，会覆盖之前的内容

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190606185020435.png)  
 通过a+，进行追加，即可达到目的

 
## []()异常处理概述

 Python程序在执行的时候，经常会遇到异常，如果中间异常不处理，经常导致程序崩溃（即：程序终止，不执行）。  
 异常处理目的就是让程序跳过这些异常，继续执行，不导致程序奔溃

 异常处理格式：  
 try:  
       正常程序  
 except Exception as 异常名称:  
        异常处理部分

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190610154310452.png)上图没有异常处理的时候，程序直接终止，不再往下执行  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190610155141497.png)上图是抛出异常，不报错  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190610165833756.png)上图是让异常后面的程序继续执行

   
  