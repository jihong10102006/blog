---
title: Applet总结
date: 2012-11-07 16:45:13
tags: CSDN迁移
---
   Java Applet是用Java编写的、含有可视化内容的、并被嵌入Web页中用来产生特殊页面效果的小程序。 

 一.Applet特点   
 1.基本的绘画功能   
 2.动态页面效果   
 3.动画和声音的播放   
 4.交互功能的实现   
 5.窗口开发环境   
 6.网络交流能力的实现   
  
二.Applet类的继承树   
   
三.Applet的主要方法及生命周期   
小应用程序生命周期中有很多不同的行为:初始化、绘画或是鼠标事件等。每一种行为都对应一个相关的方法，在Java小应用程序中有五种相对重要的方法：初始化init()、开始执行start()、停止执行stop()、退出destroy()、绘画paint()。   
1.public void init()初始化:在整个Applet生命周期中,初始化只进行一次.   
当第一次浏览含有Applet的WEB页时，浏览器将：   
 a.下载该Applet   
 b.创建对象－－产生一个该Applet主类的实例   
 c.调用init()对Applet自身进行初始化.   
 在init()方法中可设置程序初始状态,载入图形或字体,获取 HTML中 <param>设定的参数等.   
  
2.public void start()启动Applet:在整个Applet生命周期中,启动可发生多次   
在下列情况下,浏览器会调用start()方法:   
 a.Applet第一次载入时.   
 b.离开该Web页后,再次进入时(back,forward).   
c.Reload该页面时.   
 d.在浏览含有Applet的WEB页时用浏览器右上角缩放按钮缩放浏览窗口大小时.   
在start()方法中可启动一线程来控制Applet,给引入类对象发送消息,或以某种方式通知Java小应用程序开始运行.   
  
3.public void stop()停止执行Applet:在整个Applet生命周期中,停止执行可发生多次.   
在下列四种情况下,浏览器会调用stop()方法:   
 a.离开Applet所在 Web页时(用back,forward).   
 b.Reload该页面时   
 c.在浏览含有Applet的WEB页时用浏览器右上角缩放按钮缩放浏览窗口大小时.   
 d.close该Web页(彻底结束对该页面的访问).exit结束浏览器运行时(从含有该小应用程序的WEB页退出时).   
  
stop()挂起小应用程序,可释放系统处理资源.不然当浏览者离开一个页面时,小应用程序还将继续运行.   
  
4.public void paint(Graphics g)绘制:可多次发生   
  
在下列情况下,浏览器会调用paint()方法:   
  
a.Web页中含有Applet的部分被卷入窗口时.   
  
b.Applet显示区域在视线内时调整浏览窗口大小、缩放浏览窗口、移动窗口或Reload等需要重绘窗口时都会调用paint()方法.   
与前几个方法不同的是,paint()中带有一个参数Graphics g,它表明paint()需要引用一个Graphics类的对象实体.   
  
在Applet中不用编程者操心,浏览器会自动创建Graphics对象并将其传送给paint()方法.但编程者应在小应用程序中引入Graphics类所在的包   
  
import java.awt.Graphics;   
  
5.public void destroy()退出或取消:在整个Applet生命周期中,退出只发生一次.   
在彻底结束对该Web页的访问和结束浏览器运行时(close exit)调用一次.   
  
*destroy()是java.applet.Applet类中定义的方法,只能用于小应用程序.   
  
*可在该方法中编写释放系统资源的代码.但除非你用了特殊的资源如创建的线程,否则不需重写destroy()方法,因为Java运行系统本身会自动进行"垃圾"处理和内存管理.   
  
例:几个方法的调用过程AppletLife.html（在Netscape Navigator中选择Communicator->Tools->Java Console,打开Java Console进行各种操作，即可看到几个重要方法的执行情况）   


 

 

 [**Java Applet 编程技巧实例专辑**](http://vod.sjtu.edu.cn/help/Article_Show.asp?ArticleID=1586&amp;ArticlePage=7)  


 

 Java最初奉献给世人的就是Applet，随即它吸引了全世界的目光，Applet运行于浏览器上，可以生成生动美丽的页面，进行友好的人机交互，同时还能处理图像、声音、动画等多媒体数据。Applet在Java的成长过程中起到不可估量的作用，到今天Applet依然是Java程序设计最吸引的人之一。在本期专题中我将向读者介绍Applet编程的一些技巧。  
  
 Java Applet 是用Java 语言编写的一些小应用程序，这些程序是直接嵌入到页面中，由支持Java的浏览器(IE 或 Nescape)解释执行能够产生特殊效果的程序。它可以大大提高Web页面的交互能力和动态执行能力。包含Applet的网页被称为Java- powered页，可以称其为Java支持的网页。   
  
 当用户访问这样的网页时，Applet被下载到用户的计算机上执行，但前提是用户使用的是支持Java的网络浏览器。由于Applet是在用户的计算机上执行的，所以它的执行速度不受网络带宽或者Modem存取速度的限制，用户可以更好地欣赏网页上Applet产生的多媒体效果。  
  
 Applet 小应用程序的实现主要依靠java.applet 包中的Applet类。与一般的应用程序不同，Applet应用程序必须嵌入在HTML页面中，才能得到解释执行；同时Applet可以从Web页面中获得参数，并和Web页面进行交互。  
  
 含有Applet的网页的HTML文件代码中必须带有＜applet＞和＜/applet＞这样一对标记，当支持Java的网络浏览器遇到这对标记时，就将下载相应的小程序代码并在本地计算机上执行该Applet小程序。  
  
 Applet是一种Java的小程序，它通过使用该Applet的HTML文件，由支持Java的网页浏览器下载运行。也可以通过java开发工具的 appletviewer来运行。Applet 程序离不开使用它的HTML文件。这个HTML文件中关于Applet的信息至少应包含以下三点：  
  
 1)字节码文件名(编译后的Java文件，以.class为后缀)  
  
 2)字节码文件的地址  
  
 3)在网页上显示Applet的方式。  
  
 一个HTML文件增加Applet有关的内容只是使网页更加富有生气，如添加声音、动画等这些吸引人的特征，它并不会改变HTML文件中与Applet无关的元素。  
  
 (一) Applet程序开发步骤  
  
 Applet程序开发主要步骤如下：  
  
 1)选用EDIT或Windows Notepad等工具作为编辑器建立Java Applet源程序。  
  
 2)把Applet的源程序转换为字节码文件。  
  
 3)编制使用class 的HTML文件。在HTML文件内放入必要的＜APPLET＞语句。  
  
 下面举一个最简单的HelloWorld 例子来说明Applet程序的开发过程：  
  
 (1) 编辑Applet 的java源文件  
  
 创建文件夹C:\ghq，在该文件夹下建立 HelloWorld.java   
  
 文件的源代码如下：  


 **[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. import java.awt.*; 
  2. import java.applet.*; 
  3. public class HelloWorld extends Applet //继承Appelet类，这是Appelet Java程序的特点 
  4. { 
  5. public void paint(Graphics g ) 
  6. { 
  7. g.drawString("Hello World!",5,35)； 
  8. } 
  9. }   
 保存上述程序在C:\ghq\HelloWorld.java文件里。  
  
 (2)编译Applet  
  
 编译HelloWorld.java源文件可使用如下JDK命令：  
  
 C:\ghq\＞javac HelloWorld.java＜Enter＞  
 注意：如果编写的源程序违反了Java编程语言的语法规则，Java编译器将在屏幕上显示语法错误提示信息。源文件中必须不含任何语法错误，Java编译器才能成功地把源程序转换为appletviewer和浏览器能够执行的字节码程序。  
  
 成功地编译Java applet之后生成响应的字节码文件HelloWorld.class的文件。用资源管理器或DIR命令列出目录列表，将会发现目录C:\ghq中多了一个名为HelloWorld.class的文件。  
  
 (3)创建HTML文件  
  
 在运行创建的HelloWorld.class 之前，还需创建一个HTML文件，appletviewer或浏览器将通过该文件访问创建的Applet。为运行HelloWorld.class, 需要创建包含如下HTML语句的名为HelloWorld.html的文件。  
**[html]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. ＜HTML＞ 
  2. ＜TITLE＞HelloWorld! Applet＜/TITLE＞ 
  3. ＜APPLET CODE="JavaWorld.class" WIDTH=200 HEIGHT=100＞ 
  4. ＜/APPLET＞ 
  5. ＜/HTML＞   
 本例中，＜APPLET＞语句指明该Applet字节码类文件名和以像素为单位的窗口的尺寸。虽然这里HTML文件使用的文件名为 HelloWorld.HTML，它对应于HelloWorld.java的名字，但这种对应关系不是必须的，可以用其他的任何名字(比如说 Ghq.HTML)命名该HTML文件。但是使文件名保持一种对应关系可给文件的管理带来方便。  
  
 (4)执行 HelloWorld.html  
  
 如果用appletviewer运行HelloWorld.html,需输入如下的命令行：  
  
 C:\ghq\＞appletviewer JavaWorld.html＜ENTER＞  
 可以看出，该命令启动了appletviewer并指明了HTML文件，该HTML文件中包含对应于HelloWorld 的＜APPLET＞语句。  
  
 如果用浏览器运行HelloWorld Applet,需在浏览器的地址栏中输入HTML文件URL地址。  
  
 至此，一个Applet程序的开发运行整个过程结束了(包括java源文件、编译的class文件、html文件以及用appletviewer或用浏览器运行)。  
  
 (二) Applet类  
  
 Applet类是所有Applet应用的基类，所有的Java小应用程序都必须继承该类。如下所示。  
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. import java. applet.*; 
  2. public class OurApplet extends Applet 
  3. { 
  4. ...... 
  5. ...... 
  6. }   
 Applet类的构造函数只有一种，即：public Applet()  
  
 Applet实现了很多基本的方法，下面列出了Applet类中常用方法和用途。  
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. public final void setStub(AppletStub stub) 
  2. //设置Applet的stub.stub是Java和C之间转换参数并返回值的代码位，它是由系统自动设定的。 
  3. public boolean isActive();// 判断一个Applet是否处于活动状态。 
  4. public URL getDocumentBase();// 检索表示该Applet运行的文件目录的对象。 
  5. public URL getCodeBase();// 获取该Applet 代码的URL地址。 
  6. public String getParameter(String name)；// 获取该Applet 由name指定参数的值。 
  7. public AppletContext getAppletContext()；// 返回浏览器或小应用程序观察器。 
  8. public void resize(int width,int height)；// 调整Applet运行的窗口尺寸。 
  9. public void resize(Dimension d)；// 调整Applet运行的窗口尺寸。 
  10. public void showStatus(String msg)；// 在浏览器的状态条中显示指定的信息。 
  11. public Image getImage(URL url)； // 按url指定的地址装入图象。 
  12. public Image getImage(URL url,String name)；// 按url指定的地址和文件名加载图像。 
  13. public AudioClip getAudioClip(URL url)；// 按url指定的地址获取声音文件。 
  14. public AudioClip getAudioClip(URL url, String name)；// 按url指定的地址和文件名获取声音。 
  15. public String getAppletInfo()；// 返回Applet应用有关的作者、版本和版权方面的信息； 
  16. public String[][] getParameterInfo()； 
  17. // 返回描述Applet参数的字符串数组，该数组通常包含三个字符串： 参数名、该参数所需值的类型和该参数的说明。 
  18. public void play(URL url)；// 加载并播放一个url指定的音频剪辑。 
  19. public void destroy()；//撤消Applet及其所占用的资源。若该Applet是活动的，则先终止该Applet的运行。   
 (1) Applet运行状态控制基本方法  
  
 Applet类中的四种基本方法用来控制其运行状态：init()、start()、stop()、destroy()  
  
 init()方法  
  
 这个方法主要是为Applet的正常运行做一些初始化工作。当一个Applet被系统调用时，系统首先调用的就是该方法。通常可以在该方法中完成从网页向Applet传递参数，添加用户界面的基本组件等操作。  
  
 start()方法  
  
 系统在调用完init()方法之后，将自动调用start()方法。而且，每当用户离开包含该Applet的主页后又再返回时，系统又会再执行一遍 start()方法。这就意味着start()方法可以被多次执行，而不像init()方法。因此，可把只希望执行一遍的代码放在init()方法中。可以在start()方法中开始一个线程，如继续一个动画、声音等。  
  
 stop()方法  
  
 这个方法在用户离开Applet所在页面时执行，因此，它也是可以被多次执行的。它使你可以在用户并不注意Applet的时候，停止一些耗用系统资源的工作以免影响系统的运行速度，且并不需要人为地去调用该方法。如果Applet中不包含动画、声音等程序，通常也不必实现该方法。  
  
 destroy()方法  
  
 与对象的finalize()方法不同，Java在浏览器关闭的时候才调用该方法。Applet是嵌在HTML文件中的，所以destroty()方法不关心何时Applet被关闭，它在浏览器关闭的时候自动执行。在destroy()方法中一般可以要求收回占用的非内存独立资源。(如果在 Applet仍在运行时浏览器被关闭，系统将先执行stop()方法，再执行destroy()方法。  
  
 (2) Applet应用的有关参数说明  
  
 利用Applet来接收从HTML中传递过来的参数,下面对这些参数作一简单说明：  
  
 * CODE标志  
  
 CODE标志指定Applet的类名；WIDTH和HEIGHT标志指定Applet窗口的像素尺寸。在APPLET语句里还可使用其他一些标志。  
  
 * CODEBASE 标志  
  
 CODEBASE标志指定Applet的URL地址。Applet的通用资源定位地址URL，它可以是绝对地址 ，如www.sun.com。也可以是相对于当前HTML所在目录的相对地址，如/AppletPath/Name。如果HTML文件不指定 CODEBASE 标志，浏览器将使用和HTML文件相同的URL。  
  
 * ALT 标志  
  
 虽然Java在WWW上很受欢迎，但并非所有浏览器都对其提供支持。如果某浏览器无法运行Java Applet，那么它在遇到APPLET语句时将显示ALT标志指定的文本信息。  
  
 * ALIGN 标志  
  
 ALIGN标志可用来控制把Applet窗口显示在HTML文档窗口的什么位置。与HTML＜LMG＞语句一样，ALIGN标志指定的值可以是TOP、MIDDLE或BOTTOM。  
  
 * VSPACE与HSPACE 标志  
  
 VSPACE和HSPACE标志指定浏览器显示在Applet窗口周围的水平和竖直空白条的尺寸，单位为像素。如下例使用该标志在Applet窗口之上和之下各留出50像素的空白，在其左和其右各留出25像素的空白：  
  
 * NAME 标志  
  
 NAME标志把指定的名字赋予Applet的当前实例。当浏览器同时运行两个或多个Applet时，各Applet可通过名字相互引用或交换信息。如果忽略NAME标志，Applet的名字将对应于其类名。  
  
 * PARAM 标志  
  
 通用性是程序设计所追求的目标之一。使用户或者程序员能很方便地使用同一个Applet完成不同的任务是通用性的具体表现。从HTML文件获取信息是提高Applet通用性的一条有效途径。  
  
 假设编制了一个把某公司的名字在屏幕上卷动的Applet。为了使该Applet更加通用，则可以使该Applet从HTML文件获取需要卷动的文本信息。这样，若想显示另一个公司的名字，用不着修改Java Applet本身，只需修改HTML文件即可。  
  
 PARAM 标志可用来在HTML文件里指定参数，格式如下所示：  
  
 PARAM Name="name" Value="Liter"  
  
 Java Applet可调用getParameter方法获取HTML文件里设置的参数值。  
  
 显示文字是Java中最基本的功能，使用非常简单的方式来支持文字的显示，只要使用类Graphics中的drawString()函数就能实现。我们来看最简单的ghq例子：   
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. //ghq.java  
  2. import java.awt.*; 
  3. import java.applet.*; 
  4. public class ghq extends Applet 
  5. { 
  6. String text="ghq is a student!"; 
  7. public void paint(Graphics g) 
  8. { 
  9. g.drawString(text,20,20); 
  10. } //在坐标20,20 处显示text的内容  
  11. }   
 这是最基本的Java Applet，运行的时候仅显示“ghq is a student!”。Java支持Unicode，因此中文也能在Java中很好地显示出来，我们把“ghq is a student!”改成“你好！欢迎参观！”，同样可以显示(如果无法正确显示，则是浏览器的Bug，如用的IE4.0 就存在这样的问题，请改用Netscape 或IE5.0 以上版本)。值得注意的是，在Java中每个字符用16位来表示，而不是8位，这与C语言是不同的。   
  
 与用户的交互是Java的主要作用，也正是Java吸引人的原因，用户可以通过鼠标与Java Applet程序对话。我们先来看响应鼠标的例子：   
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. //Mouse.java  
  2. import java.awt.*; 
  3. import java.applet.*; 
  4. public class Mouse extends Applet 
  5. { 
  6. String text=""; 
  7. public void paint(Graphics g) 
  8. { 
  9. g.drawString(text,20,20); 
  10. } 
  11. public boolean mouseDown(Event evt,int x,int y)//鼠标按下处理函数  
  12. { 
  13. text="Mouse Down"; 
  14. repaint(); 
  15. return true; 
  16. } 
  17. public boolean mouseUp(Event evt,int x,int y)//鼠标松开处理函数  
  18. { 
  19. text=""; 
  20. repaint(); 
  21. return true; 
  22. } 
  23. }   
 当用户点击程序时，程序将显示"Mouse Down"，说明程序对鼠标作出了响应。然而要注意Java并不区分鼠标的左右键。  
  
 我们再来看对键盘响应的例子：   
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. //Keyboard.java  
  2. import java.awt.*; 
  3. import java.applet.*; 
  4. public class Keyboard extends Applet 
  5. { 
  6. String text=""; 
  7. public void paint(Graphics g) 
  8. { 
  9. g.drawString(text,20,20);} 
  10. public boolean keyDown(Event evt,int x)//键盘被按下的处理函数  
  11. { 
  12. text="Key Down"; 
  13. repaint(); 
  14. return true; 
  15. } 
  16. public boolean keyUp(Event evt,int x)//键盘被松开的处理函数  
  17. { 
  18. text=""; 
  19. repaint(); 
  20. return true; 
  21. } 
  22. } 
  23. }   
   
 当键盘被按下时，程序就会显示"Key Down"，键盘松开时清除文字。利用这些函数，我们就可以用鼠标和键盘函数与用户交互。  
  
 Java Applet常用来显示存储在GIF文件中的图像。Java Applet装载GIF图像非常简单，在Applet内使用图像文件时需定义Image对象。多数Java Applet使用的是GIF或JPEG格式的图像文件。Applet使用getImage方法把图像文件和Image对象联系起来。  
  
 Graphics类的drawImage方法用来显示Image对象。为了提高图像的显示效果，许多Applet都采用双缓冲技术：首先把图像装入内存，然后再显示在屏幕上。  
  
 Applet可通过imageUpdate方法测定一幅图像已经装了多少在内存中。   
  
 装载一幅图像  
  
 Java把图像也当做Image对象处理，所以装载图像时需首先定义Image对象，格式如下所示：  
  
 Image picture;  
 然后用getImage方法把Image对象和图像文件联系起来：  
  
 picture=getImage(getCodeBase(),"ImageFileName.GIF");   
 getImage方法有两个参数。第一个参数是对getCodeBase方法的调用，该方法返回Applet的URL地址，如 www.sun.com/Applet。第二个参数指定从URL装入的图像文件名。如果图文件位于Applet之下的某个子目录，文件名中则应包括相应的目录路径。  
  
 用getImage方法把图像装入后，Applet便可用Graphics类的drawImage方法显示图像，形式如下所示：  
  
 g.drawImage(Picture,x,y,this);  
 该drayImage方法的参数指明了待显示的图像、图像左上角的x坐标和y坐标以及this。  
  
 第四个参数的目的是指定一个实现ImageObServer接口的对象，即定义了imageUpdate方法的对象(该方法随后讨论)。   
  
 显示图像(ShowImage.java)  
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. //源程序清单 
  2. import java.awt.*; 
  3. import java.applet.*; 
  4. public class ShowImage extends Applet 
  5. Image picure; //定义类型为Image的成员变量 
  6. public void init() 
  7. { 
  8. picture=getImage(getCodeBase(),"Image.gif"); //装载图像 
  9. } 
  10. public void paint(Graphics g) 
  11. { 
  12. g.drawImage(picture,0,0,this); //显示图像 
  13. } 
  14. }   
   
 为此，HTML文件中有关Applet的语句如下：  
  
 ＜HTML＞  
 ＜TITLE＞Show Image Applet＜/TITLE＞  
 ＜APPLET  
 CODE="ShowImage.class" //class文件名为ShowImage.class  
 WIDTH=600  
 HEIGHT=400＞  
 ＜/APPLET＞  
 ＜/HTML＞  
 编译之后运行该Applet时，图像不是一气呵成的。这是因为程序不是drawImage方法返回之前把图像完整地装入并显示的。与此相反，drawImage方法创建了一个线程，该线程与Applet的原有执行线程并发执行，它一边装入一边显示，从而产生了这种不连续现象。为了提高显示效果。许多Applet都采用图像双缓冲技术，即先把图像完整地装入内存然后再显示在屏幕上，这样可使图像的显示一气呵成。  
 双缓冲图像  
  
 为了提高图像的显示效果应采用双缓冲技术。首先把图像装入内存，然后再显示在Applet窗口中。  
  
 使用双缓冲图像技术例子(BackgroundImage.java)  
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. //源程序清单 
  2. import java.awt.*; 
  3. import java. applet.*; 
  4. public class BackgroundImage extends Applet //继承Applet 
  5. { 
  6. Image picture; 
  7. Boolean ImageLoaded=false; 
  8. public void init() 
  9. { 
  10. picture=getImage(getCodeBase(),"Image.gif"); //装载图像 
  11. Image offScreenImage=createImage(size().width,size().height); 
  12. //用方法createImage创建Image对象 
  13. Graphics offScreenGC=offScreenImage.getGraphics(); //获取Graphics对象 
  14. offScreenGC.drawImage(picture,0,0,this); //显示非屏幕图像 
  15. } 
  16. public void paint(Graphics g) 
  17. { 
  18. if(ImageLoaded) 
  19. { 
  20. g.drawImage(picture,0,0,null); //显示图像，第四参数为null,不是this 
  21. showStatus("Done"); 
  22. } 
  23. else 
  24. showStatus("Loading image"); 
  25. } 
  26. public boolean imageUpdate(Image img,int infoflags,int x,int y,int w,int h) 
  27. { 
  28. if(infoflags= =ALLBITS) 
  29. { 
  30. imageLoaded=true; 
  31. repaint(); 
  32. return false; 
  33. } 
  34. else 
  35. reture true; 
  36. } 
  37. }   
 分析该Applet的init方法可知，该方法首先定义了一个名为offScreenImage的Image对象并赋予其createImage方法的返回值，然后创建了一个名为offScreenGC的Graphics对象并赋予其图形环境——非屏幕图像将由它来产生。因为这里画的是非屏幕图像，所以 Applet窗口不会有图像显示。  
  
 每当Applet调用drawImage方法时，drawImage将创建一个调用imageUpdate方法的线程。Applet可以在 imageUpdate方法里测定图像已有装入内存多少。drawImage创建的线程不断调用imageUpdate方法，直到该方法返回false为止。  
  
 imageUpdate方法的第二个参数infoflags使Applet能够知道图像装入内存的情况。该参数等于ImageLoaded设置为 true并调用repaint方法重画Applet窗口。该方法最终返回false,防止drawImage的执行线程再次调用imageUpdate方法。  
  
 该Applet在paint方法里的操作是由ImageLoaded变量控制的。当该变量变为true时，paint方法便调用drawImage方法显示出图像。paint方法调用drawImage方法时把null作为第四参数，这样可防止drawImage调用imageUpdate方法。因为这时图像已装入内存，所以图像在Applet窗口的显示可一气呵成。  
  
 使用Applet播放声音时需首先定义AudioClip对象，GetAudioClip方法能把声音赋予AudioClip对象使用Applet播放声音时需首先定义AudioClip对象，GetAudioClip方法能把声音赋予AudioClip对象，如果仅想把声音播放一遍，应调用 AudioClip类的play方法，如果想循环把声音剪辑,应选用AudioClip类的loop方法。   
  
 (1) 播放声音文件  
  
 图像格式各种各样，如BMP、GIF和JPEG等。声音文件也一样，WAV和AU是最常用的两种声音文件。目前Java仅支持AU文件，但Windows环境下常用的却是WAV文件，所以最好能有一个可把WAV文件转换为AU文件的工具。  
  
 * 播放声音的AudioClip类  
  
 AudioClip类用来在Java Applet内播放声音，该类在java.Applet包中有定义。  
  
 下面演示了如何利用AudioClip类播放声音。  
  
 装入一个名为Sample.Au的声音文件并播放(SoundDemo.java)  
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. //源程序清单 
  2. import java.awt.*; 
  3. import java.applet.* 
  4. public class SoundDemo extends Applet 
  5. { 
  6. public void paint(Graphics g) 
  7. { 
  8. AudioClip audioClip=getAudioClip(getCodeBase(),”Sample.AU”); 
  9. //创建AudioClip对象并用//getAudioClip方法将其初始化。 
  10. 
  11. 
  12. g.drawstring("Sound Demo! ",5,15); 
  13. audioClip.loop()；//使用AudioClip类的loop方法循环播放 
  14. } 
  15. }   
 需把如下的HTML语句放入SoundDemo.HTML文件，为运行该Applet做准备。  
  
 ＜HTML＞  
 ＜TITLE＞SoundDemo Applet＜/TITLE＞  
 ＜APPLET CODE="SoundDemo.class" WIDTH=300 HEIGHT=200＞  
 ＜/APPLET＞  
 ＜/HTML＞  
 编译并运行该Applet,屏幕上将显示出一个Applet窗口并伴以音乐。关闭Applet时音乐终止。  
  
 [文章导读]在Java中实现动画有很多种办法,但它们实现的基本原理是一样的,即在屏幕上画出一系列的帧来造成运动的感觉  
 Java 不仅提供了对图形、图像的支持，还允许用户实现连续的图像播放，即动画技术。Java 动画的实现，首先用Java.awt 包中的 Graphics 类的drawImage()方法在屏幕上画出图像，然后通过定义一个线程，让该线程睡眠一段时间，然后再切换成另外一幅图像；如此循环，在屏幕上画出一系列的帧来造成运动的感觉，从而达到显示动画的目的。   
  
 为了每秒钟多次更新屏幕，必须创建一个线程来实现动画的循环，这个循环要跟踪当前帧并响应周期性的屏幕更新要求；实现线程的方法有两种，可以创建一个类Thread 的派生类，或附和在一个Runnable 的界面上。  
  
 * 动画技巧  
  
 在编写动画过程时，遇到最常见的问题是屏幕会出现闪烁现象。闪烁有两个原因：一是绘制每一帧花费的时间太长(因为重绘时要求的计算量大)；二是在每次调用Pain()前，Java 会用背景颜色重画整个画面，当在进行下一帧的计算时，用户看到的是背景。  
  
 有两种方法可以明显地减弱闪烁：重载 update()或使用双缓冲。  
  
 (1) 重载 update()  
  
 当AWT接收到一个applet的重绘请求时，它就调用applet的 update()，默认地，update() 清除applet的背景，然后调用 paint()。重载 update()，将以前在paint()中的绘图代码包含在update()中，从而避免每次重绘时将整个区域清除。下面是 update()方法的原始程序代码：  
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. public void update(Graphics g) 
  2. { 
  3. //首先用背景色来绘制整个画面 
  4. g.setColor(getBackGround()); 
  5. g.fillRect(0,0,width,height); 
  6. //接着设置前景色为绘制图像的颜色，然后调用paint()方法 
  7. g.setColor(getForeGround()); 
  8. paint(g); 
  9. }   
   
 所以要消除画面闪烁就一定要改写 update() 方法，使该方法不会清除整个画面，只是消除必要的部分。  
  
 (2) 使用双缓冲技术  
  
 另一种减小帧之间闪烁的方法是使用双缓冲，它在许多动画Applet中被使用。其主要原理是创建一个后台图像，将需要绘制的一帧画入图像，然后调用 DrawImage()将整个图像一次画到屏幕上去；好处是大部分绘制是离屏的，将离屏图像一次绘至屏幕上比直接在屏幕上绘制要有效得多，大大提高做图的性能。  
  
 双缓冲可以使动画平滑，但有一个缺点，要分配一张后台图像，如果图像相当大，这将需要很大一块内存；当你使用双缓冲技术时，应重载 update()。  
  
 下面举一个时钟的例子来说明如何处理动画  
  
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. //AnimatorDemo.java 
  2. import java.util.*; 
  3. import java.awt.*; 
  4. import java.applet.*; 
  5. import java.text.*; 
  6. 
  7. 
  8. public class AnimatorDemo extends Applet implements Runnable 
  9. { 
  10. Thread timer; // 用于显示时钟的线程 
  11. int lastxs, lastys, lastxm, 
  12. lastym, lastxh, lastyh; 
  13. SimpleDateFormat formatter; //格式化时间显示 
  14. String lastdate; // 保存当前时间的字符串 
  15. Font clockFaceFont; //设置显示时钟里面的数字的字体 
  16. Date currentDate; // 显示当前时间 
  17. Color handColor; // 用于显示时针、分针和表盘的颜色 
  18. Color numberColor; // 用于显示秒针和数字的颜色 
  19. 
  20. 
  21. public void init() 
  22. { 
  23. int x,y; 
  24. lastxs = lastys = lastxm = lastym = lastxh = lastyh = 0; 
  25. formatter = new SimpleDateFormat ("yyyy EEE MMM dd hh:mm:ss "); 
  26. currentDate = new Date(); 
  27. lastdate = formatter.format(currentDate); 
  28. clockFaceFont = new Font("Serif", Font.PLAIN, 14); 
  29. handColor = Color.blue; 
  30. numberColor = Color.darkGray; 
  31. 
  32. 
  33. try { 
  34. setBackground(new Color(Integer.parseInt(getParameter("bgcolor"),16))); 
  35. } catch (Exception E) { } 
  36. try { 
  37. handColor = new Color(Integer.parseInt(getParameter("fgcolor1"),16)); 
  38. } catch (Exception E) { } 
  39. try { 
  40. numberColor = new Color(Integer.parseInt(getParameter("fgcolor2"),16)); 
  41. } catch (Exception E) { } 
  42. resize(300,300); // 设置时钟窗口大小 
  43. } 
  44. 
  45. 
  46. // 计算四分之一的圆弧 
  47. public void plotpoints(int x0, int y0, int x, int y, Graphics g) 
  48. { 
  49. g.drawLine(x0+x,y0+y,x0+x,y0+y); 
  50. g.drawLine(x0+y,y0+x,x0+y,y0+x); 
  51. g.drawLine(x0+y,y0-x,x0+y,y0-x); 
  52. g.drawLine(x0+x,y0-y,x0+x,y0-y); 
  53. g.drawLine(x0-x,y0-y,x0-x,y0-y); 
  54. g.drawLine(x0-y,y0-x,x0-y,y0-x); 
  55. g.drawLine(x0-y,y0+x,x0-y,y0+x); 
  56. g.drawLine(x0-x,y0+y,x0-x,y0+y); 
  57. } 
  58. 
  59. 
  60. // 用Bresenham算法来画圆，其中(x0,y0)是圆的中心，r为圆半径 
  61. public void circle(int x0, int y0, int r, Graphics g) 
  62. { 
  63. int x,y; 
  64. float d; 
  65. x=0; 
  66. y=r; 
  67. d=5/4-r; 
  68. plotpoints(x0,y0,x,y,g); 
  69. while (y＞x) { 
  70. if (d＜0) { 
  71. d=d+2*x+3; 
  72. x++; 
  73. } 
  74. else { 
  75. d=d+2*(x-y)+5; 
  76. x++; 
  77. y--; 
  78. } 
  79. plotpoints(x0,y0,x,y,g); 
  80. } 
  81. } 
  82. 
  83. 
  84. public void paint(Graphics g) 
  85. { 
  86. int xh, yh, xm, ym, xs, ys, s = 0, m = 10, h = 10, xcenter, ycenter; 
  87. String today; 
  88. 
  89. 
  90. currentDate = new Date(); 
  91. SimpleDateFormat formatter = new SimpleDateFormat("s",Locale.getDefault()); 
  92. try { 
  93. s = Integer.parseInt(formatter.format(currentDate)); 
  94. } catch (NumberFormatException n) { 
  95. s = 0; 
  96. } 
  97. formatter.applyPattern("m"); 
  98. try { 
  99. m = Integer.parseInt(formatter.format(currentDate)); 
  100. } catch (NumberFormatException n) { 
  101. m = 10; 
  102. } 
  103. formatter.applyPattern("h"); 
  104. try { 
  105. h = Integer.parseInt(formatter.format(currentDate)); 
  106. } catch (NumberFormatException n) { 
  107. h = 10; 
  108. } 
  109. formatter.applyPattern("EEE MMM dd HH:mm:ss yyyy"); 
  110. today = formatter.format(currentDate); 
  111. //设置时钟的表盘的中心点为(80,55) 
  112. xcenter=80; 
  113. ycenter=55; 
  114. 
  115. 
  116. // a= s* pi/2 - pi/2 (to switch 0,0 from 3:00 to 12:00) 
  117. // x = r(cos a) + xcenter, y = r(sin a) + ycenter 
  118. 
  119. 
  120. xs = (int)(Math.cos(s * 3.14f/30 - 3.14f/2) * 45 + xcenter); 
  121. ys = (int)(Math.sin(s * 3.14f/30 - 3.14f/2) * 45 + ycenter); 
  122. xm = (int)(Math.cos(m * 3.14f/30 - 3.14f/2) * 40 + xcenter); 
  123. ym = (int)(Math.sin(m * 3.14f/30 - 3.14f/2) * 40 + ycenter); 
  124. xh = (int)(Math.cos((h*30 + m/2) * 3.14f/180 - 3.14f/2) * 30 + xcenter); 
  125. yh = (int)(Math.sin((h*30 + m/2) * 3.14f/180 - 3.14f/2) * 30 + ycenter); 
  126. 
  127. 
  128. //画时钟最外面的圆盘其中心在(xcenter,ycenter)半径为50  
  129. g.setFont(clockFaceFont); 
  130. g.setColor(handColor); 
  131. circle(xcenter,ycenter,50,g); 
  132. //画时钟表盘里的数字 
  133. g.setColor(numberColor); 
  134. g.drawString("9",xcenter-45,ycenter+3); 
  135. g.drawString("3",xcenter+40,ycenter+3); 
  136. g.drawString("12",xcenter-5,ycenter-37); 
  137. g.drawString("6",xcenter-3,ycenter+45); 
  138. 
  139. 
  140. // 如果必要的话抹去然后重画  
  141. g.setColor(getBackground()); 
  142. if (xs != lastxs || ys != lastys) { 
  143. g.drawLine(xcenter, ycenter, lastxs, lastys); 
  144. g.drawString(lastdate, 5, 125); 
  145. } 
  146. if (xm != lastxm || ym != lastym) { 
  147. g.drawLine(xcenter, ycenter-1, lastxm, lastym); 
  148. g.drawLine(xcenter-1, ycenter, lastxm, lastym); } 
  149. if (xh != lastxh || yh != lastyh) { 
  150. g.drawLine(xcenter, ycenter-1, lastxh, lastyh); 
  151. g.drawLine(xcenter-1, ycenter, lastxh, lastyh); } 
  152. g.setColor(numberColor); 
  153. g.drawString("", 5, 125); 
  154. g.drawString(today, 5, 125); 
  155. g.drawLine(xcenter, ycenter, xs, ys); 
  156. g.setColor(handColor); 
  157. g.drawLine(xcenter, ycenter-1, xm, ym); 
  158. g.drawLine(xcenter-1, ycenter, xm, ym); 
  159. g.drawLine(xcenter, ycenter-1, xh, yh); 
  160. g.drawLine(xcenter-1, ycenter, xh, yh); 
  161. lastxs=xs; lastys=ys; 
  162. lastxm=xm; lastym=ym; 
  163. lastxh=xh; lastyh=yh; 
  164. lastdate = today; 
  165. currentDate=null; 
  166. } 
  167. //applet的启动方法 
  168. public void start() 
  169. { 
  170. timer = new Thread(this); 
  171. timer.start(); 
  172. } 
  173. // applet的停止方法 
  174. public void stop() 
  175. { 
  176. timer = null; 
  177. } 
  178. //线程的run方法 
  179. public void run() 
  180. { 
  181. Thread me = Thread.currentThread(); 
  182. while (timer == me) { 
  183. try { 
  184. Thread.currentThread().sleep(1000); 
  185. } 
  186. catch (InterruptedException e) { 
  187. } 
  188. repaint(); 
  189. } 
  190. } 
  191. //注意：这里重写了update()方法，只是调用了paint()方法来消除闪烁现象 
  192. public void update(Graphics g) 
  193. { 
  194. paint(g); 
  195. } 
  196. }   
   
 下面是运行该Applet 需要的AnimatorDemo.html 的内容  
  
 ＜HTML＞  
 ＜HEAD＞  
 ＜TITLE＞一个时钟的例子＜/TITLE＞  
 ＜/HEAD＞  
 ＜BODY＞  
 ＜hr＞  
 ＜applet codebase="." ALIGN=MIDDLE code="AnimatorDemo.class" width=200 height=150＞  
 ＜/applet＞  
 ＜/BODY＞  
 ＜/HTML＞  
  
 [文章导读]在有些情况下，可能需要在发生某事件时伴之以声音，尢其是在Applet 中装载图像的同时播放声音，这样将大大地丰富Applet的内容  
 在有些情况下，可能需要在发生某事件时伴之以声音，尢其是在Applet 中装载图像的同时播放声音，这样将大大地丰富Applet的内容。协调使用图像的声音是十分重要的。  
  
 声音和图像的协调(Appletl.java)  
**[java]** [ view plain](http://blog.csdn.net/c2520/article/details/8157411#)[copy](http://blog.csdn.net/c2520/article/details/8157411#)[print](http://blog.csdn.net/c2520/article/details/8157411#)[?](http://blog.csdn.net/c2520/article/details/8157411#)   
   
   
 
  1. //源程序清单 
  2. import java.awt.*; 
  3. import java.applet.*; 
  4. import java.util.*; 
  5. public class Appletl extends Applet implements Runnable 
  6. { 
  7. AudioClip audioClip; 
  8. Thread ShapeThread=null; 
  9. Random RandomNumber=new Random( ); 
  10. Color ImageColor; 
  11. public void init( ) 
  12. { 
  13. audioClip=getAudioClip(getCodeBase( ), "Sample.AU");// 创建一个AudioClip对象 
  14. } 
  15. public void start( ) 
  16. { 
  17. if (ShapeThread= =null) 
  18. { 
  19. ShapeThread=new Thread(this); 
  20. ShapeThread.start( ); 
  21. } 
  22. } 
  23. public void run() 
  24. { 
  25. while (true) 
  26. { 
  27. switch (RandomNumber.nextlnt(5)) { //把随机数转换为0~4之间的值 
  28. case 0: ImageColor=Color.black; 
  29. break; 
  30. case 1: ImageColor=Color.blue; 
  31. break; 
  32. case 2: ImageColor=Color.cyan; 
  33. break; 
  34. case3: ImageColor=Color.magenta; 
  35. break; 
  36. case4: ImageColor=Color.orange; 
  37. break; 
  38. default: ImageColor=Color.red; 
  39. } 
  40. try 
  41. { 
  42. ShapeThread.sleep(300); //线程睡眠 
  43. } 
  44. catch(InterruptedException e) 
  45. { 
  46. //忽略异常 
  47. repaint(); 
  48. } 
  49. } 
  50. public void paint(Graphics g) 
  51. { 
  52. g.setColor(ImageColor); 
  53. audioClip.play(); //播放声音 
  54. switch(RandomNumber.nextlnt(2)) //获取随机数与2整除的余数 
  55. { 
  56. case0:g.fillRect(25,25,200,200); //添充一个矩形 
  57. break; 
  58. default:g.fillOval(25,25,200,200); //添充一个椭圆 
  59. break; 
  60. } 
  61. } 
  62. }   
 该Applet的声音处理非常简单。它首先创建一个AudioClip对象并用getAudioClip把声音文件赋予该对象，然后用 AudioClip类的play方法播放声音。该Applet使用Random对象产生随机数。它首先根据随机数确定颜色；然后在paint内根据随机数确定画圆还是画方。Random类的nexsInt函数返回一个随机整数(int型)。该Applet把随机数转换为一个0~4之间的值(在run函数内)和一个0~1之间的值(在paint函数内)。  
 需把如下的HTML语句放入Appletl.HTML文件，为运行该Appletl做准备。  
  
 ＜HTML＞  
 ＜TITLE＞Applet＜/TITLE＞  
 ＜APPLET CODE="Appletl.class" WIDTH=300 HEIGHT=300＞  
 ＜/APPLET＞  
 ＜/HTML＞  
 编译并运行该Appletl，屏幕上将显示出一个Applet窗口   
 