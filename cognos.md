---
title: cognos
date: 2012-11-01 16:52:30
tags: CSDN迁移
---
   第一次听说过cognos，上网了解了关于这个内容：

 Cognos是在BI核心平台之上，以服务为导向进行架构，是唯一可以通过单一产品和在单一可靠架构上提供完整业务智能功能的解决方案。它可以提供无缝密合的报表、分析、记分卡、仪表盘等解决方案，通过提供所有的系统和资料资源，以简化公司各员工处理资讯的方法。作为一个全面、灵活的产品，Cognos业务智能解决方案可以容易地整合到现有的多系统和数据源架构中。 

 
### Cognos组件功能介绍

 **一 、Cognos 详细组件列表：** 

   
 从大模块来看， Cognos产品组件只有三个： 

   
 Cognos Powerplay Transformation Server：负责将[数据源](http://baike.baidu.com/view/286828.htm)变成数据立方体； 

   
 Cognos Powerplay Enterprise Server：负责将数据立方体以OLAP分析、OLAP报表等方式展现出来； 

   
 Cognos ReportNet Server：负责实现基于数据库的数据查询、[报表](http://baike.baidu.com/view/408928.htm)制作、仪表盘制作、报表/仪表盘展示等等； 

   
 **二 Cognos 组件功能介绍：** 

   
 我们介绍一下每个Cognos组件的功能： 

   
 Cognos Powerplay Transformation Server部分： 

   
 Cognos Impromptu：主要用来连接数据库，形成数据源定义（IQD文件），Transformer会根据数据源定义到[源数据库](http://baike.baidu.com/view/1766516.htm)中抽取数据； 

   
 Cognos Transformer：在Windows界面中提供一个图形化的模型设计界面，供开发人员设计模型和调试模型；在UNIX版本中，这个模块名称为 Cognos Powerplay Transformer UNIX Client，增加了设计界面对服务器的[控制菜单](http://baike.baidu.com/view/2062072.htm)； 

   
 Cognos Transformation Server：[后台](http://baike.baidu.com/view/179243.htm)的OLAP[数据抽取](http://baike.baidu.com/view/709638.htm)转换引擎，用来把源数据抽取出来形成数据立方体。在Windows版本中，它与前端设计界面Cognos Transformer是结合在一起的；在UNIX版本中，它与前端的模型设计界面是分离的，安装在UNIX环境中，接受命令行或来自于[客户端](http://baike.baidu.com/view/930.htm)的调度。 

   
 Cognos Powerplay Enterprise Server部分： 

   
 PowerConnect：Cognos Powerplay Enterprise Server与第三方数据立方体的连接接口，通过PowerConnect，可以将MSOLAP、Essbase、IBM DB2 OLAP、[SAP R/3](http://baike.baidu.com/view/1124367.htm) BW等第三方数据立方体通过Cognos展现出来； 

   
 Powerplay Enterprise Server：负责通过Web方式或Client方式展现数据立方体、提供OLAP界面和报表界面的服务器产品，是整个Cognos OLAP应用的核心； 

   
 Cognos Upfront：Cognos Powerplay Enterprise Server提供的门户界面，可以定制外观、功能。 

   
 Cognos ReportNet Server部分： 

   
 Cognos ReportNet Server：Cognos 负责查询、报表、仪表板的设计、制作以及展现的核心服务器模块； 

   
 Cognos Framework Manager：负责定义Cognos ReportNet Server使用的元数据，包括定义表结构、表连接、全局过滤条件、虚拟视图、业务映射等等； 

   
 Cognos Connection：Cognos ReportNet Server附送的门户界面，功能丰富，允许用户自定义内容、布局、外观、功能等等。 

   
 Cognos Access Manager 部分： 

   
 Access Manager：Cognos全部[产品的安全性](http://baike.baidu.com/view/540239.htm)管理模块，是Cognos安全性贯穿始终的基础，是Cognos安全性的核心模块； 

   
 LDAP Server：一般使用Cognos随产品附送的 Netscape/iPlanet Directory Server，或由第三方提供，用来保存Cognos安全性信息。 

   
 Cognos Powerplay Client 部分： 

   
 Cognos Powerplay Client：Cognos Powerplay Enterprise Server的Windows客户端，是强大的OLAP报表制作工具，用来制作报表，并将报表发布到 Cognos Powerplay Enterprise Server上。

   
 

   
 