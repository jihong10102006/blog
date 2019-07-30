---
title: Python网络爬虫：自动模拟HTTP请求&爬虫的异常处理&爬虫浏览器伪装技术&新闻爬虫实战
date: 2019-06-29 23:46:54
tags: CSDN迁移
---
  ## []()自动模拟HTTP请求

 客户端如果要与服务器端进行通信，需要通过http请求进行，http请求有很多种，在此使用 post与get两种请求方式。比如登录、搜索某些信息的时候会用到。  
 get：从服务器上获取数据  
 post：向服务器传送数据

 **get请求**  
 get请求可以通过URL传递信息  
 get请求实战----实现百度信息自动搜索  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625223339404.png)  
 **post请求**  
 适用于表单操作，比如登录使用  
 进行post，就需要使用urllib.request下面的Request(真实的post地址,post数据)  
 步骤：  
 1）设置post的地址  
 2）构造post的数据  
 3）请求、爬取、存储到本地  
 4）成功有对应的数据信息，没有成功就没有对应的数据信息  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190626152327387.png)

 
## []()爬虫的异常处理

 **异常处理的概述**

 爬虫在运行的过程中，经常遇到这样或那样的异常。如果没有异常处理，爬虫遇到异常时就会直接奔溃停止运行，下次再次运行时，又会从头开始，所以要开发一个具有顽强生命力的爬虫，必须要进行异常处理

 **常见状态码及含义**

 301 Moved Permanently：重定向到新的url，永久性  
 302 Found：重定向到临时的URL，非永久性  
 304 Not Modified：请求的资源未更新  
 400 Bad Request：非法请求  
 401 Unauthorized：请求未经授权  
 403 Forbidden：禁止访问  
 404 Not Found：没有找到对应页面  
 500 Internal Server Error ：服务器内部出现错误  
 501 Not Implement：服务器不支持实现请求所需要的功能

 **URLError与HTTPError**

 两者都是异常处理的类，HTTPError是URLError的子类，HTTPError有异常处理状态码与异常原因，URLError没有异常状态码，所以在处理的时候，不能使用URLError直接代替HTTPError。如果到代替，必须要判断是否有状态码属性。

 URLError出现的原因：  
 1、可能连不上服务器  
 2、远程url不存在  
 3、无网络  
 4、触发HTTPError  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190626161954522.png)  
 该页面可以爬取，故没有触发异常

 
## []()爬虫浏览器伪装技术

 若爬取的页面，返回的是403，是因为对方服务器会对爬虫进行了屏蔽。此时，我们需要伪装成浏览器才能爬取。  
 浏览器伪装我们一般通过报头进行  
 由于urlopen()对于一些HTTP的高级功能不支持，所以，我们如果要修改报头，可以使用两种方法：  
 1、urllib.request.build_opener() 修改报头伪装  
 2、urllib.request.Request()下的add_header()实现浏览器的模拟 添加报头  
 第一种方法来伪装：  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190626225332413.png)  
 第二种方法伪装：  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190628233242274.png)

 
## []()新闻爬虫实战

 需求：将搜狐新闻首页所有新闻都爬到本地  
 思路：先爬首页，通过正则获取所有新闻链接，然后依次爬各新闻，并存储到本地  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190629234256775.png)

   
  