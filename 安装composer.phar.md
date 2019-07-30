---
title: 安装composer.phar
date: 2017-12-11 17:02:53
tags: CSDN迁移
---
  Composer 是 PHP5.3以上 的一个依赖管理工具。它允许你声明项目所依赖的代码库，它会在你的项目中为你安装他们。Composer 不是一个包管理器。是的，它涉及 “packages” 和 “libraries”，但它在每个项目的基础上进行管理，在你项目的某个目录中（例如 vendor）进行安装。默认情况下它不会在全局安装任何东西。因此，这仅仅是一个依赖管理。

 安装Composer需要完成以下两步：   
 第一：下载Composer到你的项目目录。使用以下命令：   
 curl−s(Composerwebsite)/installer|php此命令只检查少量的PHP配置，然后下载composer.phar文件到你的工作目录，此文件就是Composer执行文件，它是一个PHAR（PHP归档文件，里面可以包含任何文件，并且可以在PHP命令行执行）。第二：安装Composer到指定目录，即在命令行后添加–install−diroption参数。使用以下命令： curl -s (Composer web site)/installer | php – –install-dir=bin

 这里提供一个安装包供下载：[http://download.csdn.net/download/zwj941107/9833369?utm_source=blogseo](http://download.csdn.net/download/zwj941107/9833369?utm_source=blogseo)

   
  