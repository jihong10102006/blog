---
title: SQL系统数据库
date: 2012-11-05 16:50:52
tags: CSDN迁移
---
   SQL系统数据库主要有以下数据库组成

 Master

 Model

 Tempdb

 pbus

 msdb

 Master master数据库是SQLServer系统最重要的数据库，它记录了SQLServer系统的所有系统信息，

 这些系统信息包括所有的登录信息、系统设置信息、SQLServer的初始化信息和其它系统数据库及用户数据库的相关信息。

 ModelModel数据库是所有用户数据库和Tempdb数据库的模板数据库，model数据库包含数据库目录，数据库目录是一个由17个表组成的集合；可以修改。

 Tempdb Tempdb数据库一个临时数据库，它为所有的临时表、临时存储过程及其它临时操作提供存储空间。SQL serVer仅维护单一的tempdb数据库而不管已有多少个其它数据库。

 Pubs pubs数据库是示范数据库，并非系统数据库,但是在系统安装时创建，它们可以作为SQL Server的学习工具

 Msdb msdb数据库是代理服务数据库，为其警报、任务调度和记录操作员的操作提供存储空间。

   
 