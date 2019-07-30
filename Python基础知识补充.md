---
title: Python基础知识补充
date: 2019-06-20 16:17:24
tags: CSDN迁移
---
  这里使用pycharm可打开整个Python项目  
 **pycharm的安装**  
 下载地址：[https://www.jetbrains.com/pycharm/download/#section=windows，其中professional](https://www.jetbrains.com/pycharm/download/#section=windows%EF%BC%8C%E5%85%B6%E4%B8%ADprofessional) 是专业版，需要输入激活码；Community是社区版，免费的，这里使用的专业版进行安装。  
 专业版安装流程  
 1、双击安装包，点击next----》在Destination Folder进行路径安装选择，点击next------》设置Installation Options中的 64-bit launcher，.py，点击next------》JetBrains，点击install------》Finish。  
 2、首次打开安装好的ide，会有弹窗提示：导入配置或安装文件夹/不导入配置信息，第一项是针对之前已安装过pycharm的主机，如果项目有需要，可以选择这项，一般首次安装后，是直接选择不导入配置（Do not import settings），点击OK -------->勾选同意协议，点击Continue---->定制pycharm，这个可以先skip，后面根据需求再配置插件，也可以的。  
 3、激活环节：点击Activate，点击Activationcode，输入激活码便可  
 4、配置Python解释器环境。通过File–》settings–》Project:Project Interpreter----》选择所安装的Python—》点击Apply----》点击OK

 pycharm若要调用Python控制台，需要选中pycharm IDE里面的程序，通过Alt+shift+e 进行调用

 **输入**  
 input函数  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190613170619793.png)  
 **运算符**  
 ** 代表幂次方  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190618140404984.png)  
 **切片运算**  
 是一种用于取部分数据的运算，比如取字符串、取列表元组等的部分数据等。  
 注：取部分也包含自己本身  
 格式：名称[ : ]  
 解释：方框中冒号的左边是取得开始位置，冒号右边取得是结束的位置+1，其中下图中的负号是从后开始  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190618171916306.png)  
 **列表、元组、字典的常用操作**  
 列表的遍历  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190618174741814.png)  
 元组的遍历  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190618175554108.png)  
 字典遍历  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190618181205437.png)  
 列表与字典的组合遍历  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190618182749841.png)**递归函数**  
 调用自己本身的函数称为递归函数  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190619181945383.png)  
 **匿名函数**  
 匿名函数：没有名字的函数。匿名函数通过lambda表达式来表示  
 格式：  
 lambda 参数1，参数2：对应的函数体  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190619182654969.png)  
 **文件复制**  
 文件的复制是把文件从一个地方复制到另一个地方，通过如下操作：  
 shutil.copy(源地址,目标地址)  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190619183832569.png)上图中的案例是把文件中的图片102.jpg复制到其它位置，经查询已复制过去

 **文件的删除与重命名**  
 格式：  
 import os  
 os.remove(要删除的文件路径)  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620104519877.png)  
 上图中的102.jpg已删除

 import os  
 os.rename(“原文件名”,“新文件名”)  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620104922694.png)  
 上图中 把图片103.jpg重命名了1031 .jpg

 **文件夹相关操作**  
 创建目录：  
 格式：  
 import os  
 os.mkdir(要创建的目录的路径)  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2019062010553675.png)  
 重命名目录：  
 import os  
 os.rename(“原目录位置”,“新目录位置”)  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620105740818.png)  
 展现目录名：  
 import os  
 变量1=os.listdir(对应的目录路径)  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620110147229.png)  
 删除目标路径：  
 import os  
 os.rmdir(对应的要删除的目录路径)  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620110316815.png)  
 **面向对象魔术方法**  
 魔术方法：在特定的情况下会自动触发的方法。最常见的是构造方法和析构方法  
 构造方法是在对象构建的时候自动触发的方法 _ _init_ _（self）  
 析构方法是在该对象销毁前一刻自动触发的方法 _ _del_ _(self)  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620112956855.png)**自定义异常**  
 异常分为标准异常（Python中定义好的）和自定义异常（我们自己定义的）  
 标准异常：[https://docs.python.org/3/library/exceptions.html#bltin-exceptions](https://docs.python.org/3/library/exceptions.html#bltin-exceptions)  
 常见格式1：  
 class 自定义异常类型名(Exception):  
 def _ _init_ _(self,变量1)：  
 self.变量1=变量1  
 def _ _str_ _(self):  
 return self.变量1  
 这里的str函数代表怎么输出  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620135433547.png)  
 后面需要定义在什么情况下调用该异常

 **异常抛出**  
 即使程序运行时在实际上没有出现错误，你也可以在程序的某一个位置主动的设置引发某个异常，由我们主动引发异常的这种行为我们叫做异常的抛出。  
 格式：  
 raise 异常类型(提示信息)  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620135946132.png)  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2019062014072049.png)  
 **自定义模块**  
 自定义模块分为：简单模块和复杂模块。模块需要放在Python安装目录下的Lib目录中  
 简单模块：  
 import 模块文件  
 如：import pr  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2019062014125081.png)  
 把这个pr.py放到安装Python目录中的Lib下，就成为一个模块，然后进行调用，如下图所示  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620141416583.png)  
 复杂的模块：  
 由多个.py文件组成的模块，一般放入文件中，该文件夹放在安装Python目录下的Lib目录下的site-packages中，如：D:\python\Lib\site-packages  
 格式：import 模块名.封装的脚本名称  
 如：import fac.dofac  
 _文件中必须有形同虚设的_ _pycahe_ _名字的文件夹，_ _init_ _.py的脚本文件，这两个里面可以没有任何东西，但是必须有这两个文件，还有封装的方法_，如下图所示：  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620152412491.png)  
 docfac.py中的脚本如下：  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620152449744.png)  
 导入如下：fac模块下的  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620152602485.png)  
 **模块导入的三种方式**  
 1、import 模块名  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620153613811.png)  
 2、from 模块名 import 方法名  
 因只导入了方法名，故能使用导入的方法，不能使用其他方法，也不能使用该模块名  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620160204587.png)  
 3、from 模块名 import *  
 *代表是把模块中的所有方法都导进来，但是没有导这个模块，故该模块不可以使用  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620160652954.png)  
 **如何查看模块功能**  
 当接触到一个新模块的时候，如何了解这个模块的功能。  
 主要方法有：  
 1、help（）–》回车----》输入对应的模块名  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620175110328.png)  
 如果不知道安装了哪些模块，可以通过cmd–》pip list进行查看  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620175226223.png)  
 2、阅读该模块的文档，一些大型的模块都有，比如scrapy 等  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620175412151.png)  
 3、查看模块的源代码，分析各方法的作用，当然也可以从名字进行相应的分析  
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190620175747186.png)

   
  