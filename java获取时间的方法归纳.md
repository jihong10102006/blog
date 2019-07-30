---
title: java获取时间的方法归纳
date: 2012-11-09 16:25:48
tags: CSDN迁移
---
   一、获取当前时间, 格式为: yyyy-mm-dd hh-mm-ss 

 DateFormat.getDateTimeInstance(2, 2, Locale.CHINESE).format(new java.util.Date());

 

 二、获取当前时间, 格式为: yyyy年mm月dd日 上午/下午hh时mm分ss秒

 DateFormat.getDateTimeInstance(DateFormat.LONG, DateFormat.LONG, Locale.CHINESE).format(new java.util.Date());

 

 三、获取当前时间(精确到毫秒), 格式为: yyyy-mm-dd hh:mm:ss.nnn

 new java.sql.Timestamp(System.currentTimeMillis()).toString();

   
 