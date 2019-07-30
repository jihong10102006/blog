---
title: 四  （01）、自动化测试-----WebDriver API
date: 2018-06-28 16:20:35
tags: CSDN迁移
---
  一、从定位元素开始   
 WebDriver提供了八种元素定位方法:   
 1、id 2、name 3、class name 4、tag name 5、link text 6、partial link text 7、XPath 8、css selector 在Python语言中，对应的定位方法如下：   
 find_element_by_id()   
 find_element_by_name()   
 find_element_by_class_name()   
 find_element_by_tag_name()   
 find_element_by_link_text()   
 find_element_by_partial_link_text() 有些文本链接会很长，可以取文本链接的一部分定位   
 find_element_by_xpath()   
 find_element_by_css_selector()

 XPath定位   
 1）XPath可以通过 写出元素的绝对路径，即：绝对地址   
 2）XPath也可通过元素属性值来定位   
 find_element_by_xpath(“//input[@ id =’kw’]”)   
 //表示当前页面某个目录下，input表示定位元素的标签名，[@ id=’kw‘]表示这个元素的id属性值等于kw   
 3）XPath也可通过层级与属性相结合   
 4）XPath也可通过逻辑运算符连接多个属性来查找元素

 CSS定位   
 1）通过CSS属性定位： .（点号）表示通过class属性来定位元素   
 2）通过id属性定位：（#）井号表示通过id属性来定位元素   
 3）通过标签名定位 ：如： input   
 4）通过父子关系定位   
 find_element_by_css_selector(“span>input”) 表示有父亲元素，它的标签名为span,查找它的所有标签名叫input的子元素   
 5）通过属性定位：   
 find_element_by_css_selector(“[autocomplete=off]”)   
 6）组合定位   
 XPath与CSS定位方式对比

 
     定位       | XPath                           | CSS                                                                              
     -------- | ------------------------------- | --------------------------------------------------------------------------------- 
     标签       | //div                           | div                                                                              
     By id    | //div[@id=’eleid’]              | div #eleid                                                                       
     By class | //div[@class=’eleclass’]        | div.eleclass                                                                     
     By属性     | //div[@title=’move mouse here’] | div[title=move mouse here]   div[title^=move]  div[title$=here] div[title*=mouse]
     定位子元素    | //div[@id=’eleid’]/*  //div/h1  | div#eleid&gt;*  div&gt;h1                                                        

 二、控制浏览器   
 一）控制浏览器大小   
 WebDriver提供了**set_window_size()**方法来设置浏览器大小   
 浏览器在全屏模式下，可以使用**maximize_window()**方法使打开的浏览器全屏显示，其用法与set_window_size()相同，但它不需要参数

 
```
from selenium import webdriver
from time import *
driver=webdriver.Firefox()
driver.get("https://www.baidu.com/")
print("设置浏览器宽480，高800显示")
driver.set_window_size(480,800)
sleep(5)
driver.maximize_window()
sleep(5)
driver.quit()
```
 二） 控制浏览器的前进与后退   
 WebDriver提供back( )和forward（）方法来模拟后退和前进按钮

 
```
from selenium import webdriver
from time import *
driver=webdriver.Firefox()
first_url='https://www.baidu.com/'
print("now access %s"%first_url)
driver.get(first_url)

second_url='http://news.baidu.com/'
print("now access %s"%second_url)
driver.get(second_url)

driver.back()
print("now access %s"%first_url)
sleep(5)

driver.forward()
print("now access %s"%second_url)
sleep(5)

driver.quit()
```
 运行结果：   
 ![这里写图片描述](https://img-blog.csdn.net/20180626175454539?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppaG9uZzEwMTAyMDA2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 三）控制浏览器刷新   
 在使用浏览器浏览网页时，浏览器需要刷新来浏览最新的数据，可以手动刷新（F5）页面，WebDriver提供对应refresh()方法来模拟刷新。

 
```
from selenium import webdriver
from time import *
driver=webdriver.Firefox()

first_url='https://www.baidu.com/'
print("now access %s"%first_url)
driver.get(first_url)

second_url='http://news.baidu.com/'
print("now access %s"%second_url)
driver.get(second_url)

driver.back()
print("now access %s"%first_url)
sleep(5)

driver.forward()
print("now access %s"%second_url)
sleep(5)

driver.refresh()
sleep(5)

driver.quit()
```
 三、简单元素操作   
 定位元素后，需要对该元素进行操作或单击（按钮）或输入（输入框），WebDriver中常用的方法：   
 clear（） ：清除文本   
 send_keys(* value) : 模拟按键输入   
 click（）：单击元素

 一）126邮箱登陆方式

 
```
from selenium import webdriver
from time import *
driver=webdriver.Firefox()

first_url='https://mail.126.com/'
driver.get(first_url)


driver.switch_to_frame("x-URS-iframe")
driver.find_element_by_xpath("//input[@class='j-inputtext dlemail']").clear()
driver.find_element_by_xpath("//input[@class='j-inputtext dlemail']").send_keys("输入具体用户名")

driver.find_element_by_xpath("//input[@class='j-inputtext dlpwd']").clear()
driver.find_element_by_xpath("//input[@class='j-inputtext dlpwd']").send_keys("输入对应的密码")

driver.find_element_by_id("dologin").click()

sleep(5)
driver.quit()
```
 二）WebElement 接口常用方法   
 通常需要与页面交互的方法都由WebElement接口提供，包括上面的8中定位方法和刚才的3中方法。除此之外，WebElement还提供了如下方法：   
 submit（） 用于提交表单。如：在搜索框输入关键字之后的“回车”操作，就可以通过submit()方法模拟。

 
```
from selenium import webdriver
from time import *
driver=webdriver.Firefox()

first_url='http://www.youdao.com/'
driver.get(first_url)

driver.find_element_by_id("translateContent").send_keys("hello")
driver.find_element_by_xpath("//*[@id='form']/button").submit()

sleep(5)
driver.quit()
```
 size ：返回元素的尺寸   
 text：获取元素的文本   
 get_attribute(name)：获取属性值   
 is_displayed()：判断该元素是否用户可见

 
```
from selenium import webdriver
from time import *
driver=webdriver.Firefox()

driver.get("https://www.baidu.com/")
size=driver.find_element_by_id("kw").size
print(size)

text=driver.find_element_by_id("cp").text
print(text)

result=driver.find_element_by_id("kw").is_displayed()
print(result)

sleep(5)
driver.quit()
```
 四、鼠标事件   
 ActionChains类提供了鼠标操作的常用方法：   
 click（on_element=None）——–单击鼠标左键   
 click_and_hold（on_element=None）——–单击鼠标左键，不松开   
 context_click（on_element=None）——–单击鼠标右键   
 double_click（on_element=None）——–双击鼠标左键   
 drag_and_drop（on_element=None）——–拖拽到 某个元素后松开   
 drag_and_drop_by_offset（source，xoffset，yoffset）——–拖拽到 某个坐标后 松开   
 move_by_offset（xoffset，yoffset）——–鼠标从当前位置移动到某个坐标   
 move_to_element（to_element）——–鼠标移动到某个元素   
 drag_and_drop_by_offset（source，xoffset，yoffset）——–拖拽到 某个坐标后 松开   
 move_to_element_with_offset（to_element，xoffset，yoffset）——–移动到距离某个元素（左上角坐标）多少距离的位置   
 perform（）——–执行链中的所有动作   
 release（on_element=None）——–在某个元素位置松开鼠标左键   
 send_keys（*keys_to_send）——–发送某个键到当前焦点的元素   
 send_keys_to_element（element，*keys_to_send）——–发送某个键到指定元素

 一）鼠标右击操作   
 假如：目标网址：[http://sahitest.com/demo/clicks.htm](http://sahitest.com/demo/clicks.htm)

 
```
from selenium import webdriver
from selenium.webdriver.common.action_chains import ActionChains
from time import *
driver=webdriver.Firefox()

driver.get("http://sahitest.com/demo/clicks.htm")
driver.implicitly_wait(10)

rightclick_btn=driver.find_element_by_xpath("html/body/form/input[4]")

ActionChains(driver).context_click(rightclick_btn).perform()
print(driver.find_element_by_name("t2").get_attribute("value"))

sleep(5)
driver.quit()
```
 二）鼠标悬停与移动   
 鼠标悬停弹出下拉菜单也是一个十分常见的功能设计   
 move_to_element()方法可以模拟鼠标悬停的动作，其用法与context_click()相同

 
```
from selenium import webdriver
from selenium.webdriver.common.action_chains import ActionChains
from time import *
driver=webdriver.Firefox()

driver.get("http://sahitest.com/demo/clicks.htm")
driver.implicitly_wait(10)

rightclick_btn=driver.find_element_by_xpath("html/body/form/input[4]")

ActionChains(driver).move_to_element(rightclick_btn).perform()

sleep(5)
driver.quit()
```
 假如：目标网址：[http://sahitest.com/demo/mouseover.htm](http://sahitest.com/demo/mouseover.htm)

 
```
from selenium import webdriver
from selenium.webdriver.common.action_chains import ActionChains
from time import *
driver=webdriver.Firefox()

driver.get("http://sahitest.com/demo/mouseover.htm")
driver.implicitly_wait(10)
driver.maximize_window()

write=driver.find_element_by_xpath("html/body/form/input[1]")

blank=driver.find_element_by_xpath("html/body/form/input[2]")

result=driver.find_element_by_name("t1")

action=ActionChains(driver)

action.move_to_element(write).perform()
print(result.get_attribute("value"))
sleep(5)

#action.move_to_element(blank).perform()
action.move_by_offset(10,50).perform()
print(result.get_attribute("value"))
sleep(5)

action.move_to_element_with_offset(blank,10,-40).perform()
print(result.get_attribute("value"))

sleep(5)
driver.quit()
```
 三）鼠标双击操作   
 double_click()方法用于模拟鼠标双击操作。   
 目标网址：[http://sahitest.com/demo/clicks.htm](http://sahitest.com/demo/clicks.htm)

 
```
from selenium import webdriver
from selenium.webdriver.common.action_chains import ActionChains
from time import *
driver=webdriver.Firefox()

driver.get("http://sahitest.com/demo/clicks.htm")
driver.implicitly_wait(10)
driver.maximize_window()

doubleclick_btn=driver.find_element_by_xpath("html/body/form/input[2]")
action=ActionChains(driver)
action.double_click(doubleclick_btn).perform()
print(driver.find_element_by_name("t2").get_attribute("value"))

sleep(5)
driver.quit()
```
 四）鼠标拖放操作   
 drag_and_drop(source，target)在源元素上按住鼠标左键，然后移动到目标元素上释放。   
 source：鼠标拖动的源元素   
 target：鼠标释放的目标元素   
 目标网址：[http://sahitest.com/demo/dragDropMooTools.htm](http://sahitest.com/demo/dragDropMooTools.htm)

 
```
from selenium import webdriver
from selenium.webdriver.common.action_chains import ActionChains
from time import *
driver=webdriver.Chrome()

driver.get("http://sahitest.com/demo/dragDropMooTools.htm")
driver.implicitly_wait(10)
#driver.maximize_window()

dragger=driver.find_element_by_id("dragger")

item1=driver.find_element_by_xpath("html/body/div[2]")

item2=driver.find_element_by_xpath("html/body/div[3]")

item3=driver.find_element_by_xpath("html/body/div[4]")

item4=driver.find_element_by_xpath("html/body/div[5]")

action=ActionChains(driver)
action.drag_and_drop(dragger,item1).perform()
sleep(5)

action.click_and_hold(dragger).release(item2).perform()
sleep(5)

action.drag_and_drop_by_offset(dragger,300,150).perform()
sleep(5)

action.click_and_hold(dragger).move_by_offset(400,100).perform()
sleep(5)

driver.quit()
```
 五、键盘事件   
 Keys()类提供了键盘上几乎所有按键的方法，前面，send_keys()可以用来模拟键盘输入，除此之外，还可以用它来输入键盘上的按键，甚至是组合键   
 key_down(value,element=None)———-按下某个键盘上的键   
 key_up(value,element=None)———-松开某个键   
 常用的键盘操作：   
 send_keys(Keys.BACK_SPACE) ——删除键（backspace）   
 send_keys(Keys.SPACE)———— 空格键（space）   
 send_keys(Keys.TAB) ———-制表键（Tab）   
 send_keys(Keys.ESCAPE)———-回退键（esc）   
 send_keys(Keys.ENTER) ———回车键（enter）   
 send_keys(Keys.CONTROL,’a’)———–全选（ctrl+A）   
 send_keys(Keys.CONTROL,’c’)—————复制（ctrl+C）   
 send_keys(Keys.CONTROL,’x’)——–剪切（ctrl+X）   
 send_keys(Keys.CONTROL,’v’)—————粘贴（ctrl+V）   
 send_keys(Keys.F1)—————键盘F1   
 ……..   
 send_keys(Keys.F12)———— 键盘F12 

 
```
from selenium import webdriver
from selenium.webdriver.common.action_chains import ActionChains
from selenium.webdriver.common.keys import Keys
from time import *
driver=webdriver.Firefox()

driver.get("https://www.baidu.com")
driver.implicitly_wait(10)

driver.find_element_by_id("kw").send_keys("seleniumm")
sleep(5)

driver.find_element_by_id("kw").send_keys(Keys.BACK_SPACE)
sleep(5)

driver.find_element_by_id("kw").send_keys(Keys.SPACE)
sleep(5)

driver.find_element_by_id("kw").send_keys("教程")
sleep(5)

driver.find_element_by_id("kw").send_keys(Keys.CONTROL,"a")
sleep(5)

driver.find_element_by_id("kw").send_keys(Keys.CONTROL,"x")
sleep(5)

driver.find_element_by_id("kw").send_keys(Keys.CONTROL,"v")
sleep(5)

driver.find_element_by_id("kw").send_keys(Keys.ENTER)
sleep(5)

driver.quit()
```
 目标网址：[http://sahitest.com/demo/keypress.htm](http://sahitest.com/demo/keypress.htm)

 
```
from selenium import webdriver
from selenium.webdriver.common.action_chains import ActionChains
from selenium.webdriver.common.keys import Keys
from time import *
driver=webdriver.Firefox()

driver.get("http://sahitest.com/demo/keypress.htm")
driver.implicitly_wait(10)
driver.maximize_window()
action=ActionChains(driver)

key_up_radio=driver.find_element_by_id("r1")
key_down_radio=driver.find_element_by_id("r2")
key_press_radio=driver.find_element_by_id("r3")
enter=driver.find_element_by_xpath("html/body/form/input[2]")
result=driver.find_element_by_xpath("html/body/form/input[1]")

key_down_radio.click()
action.key_down(Keys.CONTROL,enter).key_up(Keys.CONTROL,enter).perform()
print(result.get_attribute("value"))
sleep(5)

key_up_radio.click()
enter.click()
action.key_down(Keys.SHIFT).key_up(Keys.SHIFT).perform()
print(result.get_attribute('value'))
sleep(5)

key_press_radio.click()
action.send_keys("a").perform()
print(result.get_attribute('value'))
sleep(5)

driver.quit()
```
   
  