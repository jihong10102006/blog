---
title: 二、自动化测试----python等工具下载、测试环境搭配、常用的DOS命令
date: 2018-06-24 22:39:59
tags: CSDN迁移
---
  **一、Python等工具的下载**   
 Python 下载地址：[https://www.python.org/downloads/](https://www.python.org/downloads/)   
 setuptools 下载地址：[https://pypi.org/project/setuptools/#files](https://pypi.org/project/setuptools/#files)   
 distribute 下载地址 ：[https://pypi.org/project/distribute/#files](https://pypi.org/project/distribute/#files)

 **二、setuptools与pip说明**   
 setuptools是python的disutils工具的增强工具，可以让程序员更方便地创建和发布Python包，特别是那些对其他包有依赖性的状况。   
 使用easy_install命令时，是在调用setuptools来完成安装模块的工作。   
 pip是一个安装和管理pyhon包的工具，通过pip来安装Python包变得十分简单，省去了搜索-查找版本-下载-安装等繁琐过程。

 **注意：**   
 Python 3并不支持setuptools，因此使用distribute

 **三、测试环境搭建**   
 Python自带pip ，只需要把下载好的 distribute 和setuptools放到安装好的Python中   
 1、查看pip安装情况   
 通过cmd–》输入 pip   
 ![这里写图片描述](https://img-blog.csdn.net/20180623223837878?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)   
 输入pip list   
 ![这里写图片描述](https://img-blog.csdn.net/20180623225031795?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)   
 查看pip的是否安装好以及setuotools等相关信息 

 2、进入distribute 安装selenium   
 找到distribute所在的路径粘贴到该DOS环境中，输入 python setup.py   
 ![这里写图片描述](https://img-blog.csdn.net/20180623225433491?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 输入 pip install selenium   
 ![这里写图片描述](https://img-blog.csdn.net/20180623224538965?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)   
 等待片刻，selenium安装完毕

 到此，测试环境搭配完成。

 **四、常见的DOS命令**

 
     常见的DOS命令             | 说明                    
     -------------------- | ---------------------- 
     d:+回车                | 列出当前目录下的文件以及文件夹       
     dir(directory)       | 列出当前目录下的文件以及文件夹       
     cd（change directory） | 显示指定目录                
     cd..                 | 退回到上一级目录              
     cd\\                 | 退回到根目录                
     cls（clear screen）    | 清屏                    
     exit                 | 退出dos命令行              
     md（make directory）   | 创建目录                  
     rd（remove directory） | 删除目录                  
     del（delete）*.txt     | 删除文件，删除一堆后缀名一样的文件*.txt
     notepad              | 创建文件                  
     rd + /s + 文件夹名称      | 删除带内容的文件，询问是否删除       
     rd + /q + /s +文件夹名称  | 删除带内容的文件，直接删除         

 **五、用IDLE编写python**   
 快捷键：   
 tap键 补全代码   
 回退代码语句   
 Alt+p 或者Alt+n 前者从后往前后退， 后者从前往后 后退

 **六、编写第一个自动化脚本**   
 在IDLE中编写

 
```
from selenium import webdriver

driver=webdriver.Firefox()
driver.get("https://www.baidu.com")

driver.find_element_by_id("kw").send_keys("selenium2")
dirver.find_element_by_id("su").click()

#dirver.quit()
```
 运行结果出现如下问题：   
 ![这里写图片描述](https://img-blog.csdn.net/20180624170812843?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 
> 经测试，可以成功，使用的版本如下：   
>  Firefox 版本：60.0.2（32位）   
>  pip 版本：9.0.1   
>  distribute 版本：0.7.3   
>  selenium 版本：3.12.0   
>  setuptools 版本：28.8.0
> 
>  
 windows系统解决办法如下：   
 1）下载geckodriver.exe:   
 下载地址：[https://github.com/mozilla/geckodriver/releases](https://github.com/mozilla/geckodriver/releases)   
 根据系统版本选择下载（如：Windows 64位系统）   
 2）下载解压后将geckodriver.exe复制到Firefox的安装目录下，如（D:\火狐浏览器\Mozilla Firefox），并在环境变量path中添加路径：D:\火狐浏览器\Mozilla Firefox   
 3）重启cmd或IDLE再次运行代码

 **七、安装浏览器驱动**   
 WebDriver支持Firefox(FirefoxDriver)、IE（InternetExploerDriver）、Opera（OperaDriver）和Chrome（ChromeDriver）等浏览器。除此之外，它还支持Andriod（AndriodDriver）和iPhone（iPhoneDriver）的移动应用测试。   
 各个浏览器驱动下载地址：[https://www.seleniumhq.org/download/](https://www.seleniumhq.org/download/)

 **八、不同编程语言下使用WebDriver**   
 步骤：   
 1）首先导入Selenium（Webdriver）相关模块。   
 2）调用Selenium的浏览器驱动，获取浏览器句柄（driver）并启动浏览器。   
 3）通过句柄访问百度URL   
 4）通过句柄操作页面元素（百度输入框和按钮）   
 5）通过句柄关闭浏览器。

   
  