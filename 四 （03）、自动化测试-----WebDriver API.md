---
title: 四 （03）、自动化测试-----WebDriver API
date: 2018-07-09 13:38:42
tags: CSDN迁移
---
  十五、调用javasript   
 借助JavaScript 方法来控制浏览器滚动条。WebDriver 提供了execute_script()方法来执行JavaScript 代码。   
 window.scrollTo()方法用于设置浏览器窗口滚动条的水平和垂直位置。方法的第一个参数表示水平的左间距，第二个参数表示垂直的上边距

 
```
from selenium import webdriver
from time import *

driver=webdriver.Chrome()
driver.get("https://www.baidu.com")

driver.set_window_size(800,600)
driver.find_element_by_id("kw").send_keys("selenium")
driver.find_element_by_id("su").click()
sleep(5)

js="window.scrollTo(100,450)"
driver.execute_script(js)

sleep(5)
driver.quit()
```
 十六、处理HTML5的视频

 
```
from selenium import webdriver
from time import *

driver=webdriver.Chrome()
driver.get("http://videojs.com/")

video=driver.find_element_by_xpath(".//*[@id='preview-player_html5_api']")
url=driver.execute_script("return arguments[0].currentsrc;",video)
print(url)

print("start")
driver.execute_script("return arguments[0].play(0)",video)

sleep(15)

print("stop")
driver.execute_script("return arguments[0].pause();",video)

sleep(5)
driver.quit()
```
 十七、窗口截图   
 Webdriver提供了截图函数get_screenshot_as_file()来截取当前窗口

 
```
from selenium import webdriver
from time import *

driver=webdriver.Chrome()
driver.get("https://www.baidu.com/")

driver.find_element_by_id("kw").send_keys("selenium")
driver.find_element_by_id("su").click()
sleep(5)

driver.get_screenshot_as_file(r"C:\Users\Administrator\Desktop\baidu.jpg")

sleep(5)
driver.quit()
```
 十八、关闭窗口   
 Webdriver提供如下：   
 quit()，退出相关的驱动程序和关闭所有窗口   
 close()，关闭当前窗口

 十九、验证码的处理   
 1）去掉验证码   
 2）设置万能验证码

 
```
from selenium import webdriver
from time import *
from random import randint

verify=randint(1000,9999)
print("随机数：%d"%verify)

number=input("请输入随机数:")
print(number)
number=int(number)

if number==verify:
    print("OK")
elif number==123741:
    print("OK")
else:
    print("no ok")
```
 3)记录cookie

   
  