---
title: 四  （02）、自动化测试-----WebDriver API
date: 2018-07-06 17:26:05
tags: CSDN迁移
---
  六、获取验证信息   
 通常用得最多的几种验证信息分别是title、URL、text。用于获取标签对之间的文本信息

 
```
from selenium import webdriver
from time import *
driver=webdriver.Firefox()

driver.get('https://mail.126.com/')

print("before login....................")
title=driver.title
print(title)
now_url=driver.current_url
print(now_url)


driver.switch_to_frame("x-URS-iframe")
driver.find_element_by_xpath("//input[@class='j-inputtext dlemail']").clear()
driver.find_element_by_xpath("//input[@class='j-inputtext dlemail']").send_keys("邮箱用户名")

driver.find_element_by_xpath("//input[@class='j-inputtext dlpwd']").clear()
driver.find_element_by_xpath("//input[@class='j-inputtext dlpwd']").send_keys("邮箱密码")

driver.find_element_by_id("dologin").click()

sleep(5)

print("after login.................")
title=driver.title
print(title)
now_url=driver.current_url
print(now_url)
user=driver.find_element_by_id("spnUid").text
print(user)

sleep(5)
driver.quit()
```
 七、设置元素等待   
 如今大多数Web应用程序使用AJAX技术。当浏览器在加载页面时，页面上的元素可能并不是同时被加载完成，这给元素的定位增加了困难。如果因为在加载某个元素时延迟而造成ElemetNotVisibleException的情况出现，那么就会降低自动化脚本的稳定性，我们可以通过设置元素等待改善这种问题造成的不稳定。   
 Webdriver 提供了两种类型的等待：显示等待和隐式等待   
 一）显示等待   
 显示等待使Webdriver等待某个条件成立时继续执行，否则在达到最大时长时抛出超时异常（TimeoutException）

 
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

from time import *
driver=webdriver.Firefox()
driver.get("https://www.baidu.com/")
driver.maximize_window()

element=WebDriverWait(driver,5,0.5).until(EC.presence_of_element_located((By.ID,"kw")),message="无法定位")
element.send_keys("selenium")

sleep(5)
driver.quit()
```
 WebDriverWait(driver,timeout,poll_frequency=0.5,ignored_exceptions=None)   
 driver：浏览器驱动   
 timeout：最长超时时间，默认以秒为单位   
 poll_frequency：检测的间隔（步长）时间，默认为0.5 s   
 ignored_exceptions：超时后的异常信息，默认情况下抛NoSuchElementException异常   
 WebDriverWait()一般由until()或until_not()方法配合使用，下面是until()和until_not()方法的说明   
 until(method,message=”“)   
 调用该方法提供的驱动程序作为一个参数，直到返回值为True   
 until_not(method,message=”“)   
 调用该方法提供的驱动程序作为一个参数，直到返回值为False   
 通过as关键字将expected_conditions充命名为EC，并调用presence_of_element_located()方法判断元素是否存在

 expected_conditions类所提供的预期条件判断的方法

 
     方法                                     | 说明                                                            
     -------------------------------------- | -------------------------------------------------------------- 
     title_is                               | 判断当前页面的标题是否等于预期                                               
     title_contains                         | 判断当前页面的标题是否包含预期字符串                                            
     presence_of_element_located            | 判断元素是否被加在DOM里，并不代表该元素一定可见                                     
     visibility_of_element_located          | 判断元素是否可见（可见代表元素非隐藏，并且元素的宽和高都不等于0）                             
     visibility_of                          | 与上一个方法相同，只是上一个方法参数为定位，该方法接收的参数为定位后的元素                         
     presence_of_all_elements_located       | 判断是否至少有一个元素存在于DOM树中。例如，在一个页面中有n个元素的class为“wp”，那么只要有一个存在就返回True
     text_to_be_present_in_element          | 判断某个元素的text是否包含预期的字符串                                         
     text_to_be_present_in_element_value    | 判断某个元素的value属性是否包含预期的字符串                                      
     frame_to_be_available_and_switch_to_it | 判断该表单是否可以切换过去，如果可以，返回True并且switch进去，否则返回False                 
     invisibility_of_elment_located         | 判断某个元素是否不存在于DOM树或不可见                                          
     element_to_be_clickable                | 判断元素是否可见并且是可以点击的                                              
     staleness_of                           | 等到一个元素从DOM树中移除                                                
     element_to_be_selected                 | 判断某个元素是否被选中，一般用在下拉列表                                          
     element_selection_state_to_be          | 判断某个元素的选中状态是否符合预期                                             
     element_located_selection_state_to_be  | 与上一个方法作用相同，只是上一个方法参数为定位后的元素，该方法接收的参数为定位                       
     alert_is_present                       | 判断也页面上是否存在alert                                               

 还可以使用之前的is_displayed()来判断元素是否可见

 
```
from selenium import webdriver
from time import *

driver=webdriver.Firefox()
driver.get("https://www.baidu.com/")
driver.maximize_window()

print(ctime())
for i in range(10):
    try:
        element=driver.find_element_by_id("kw")
        if element.is_displayed():
            break
        else:
            sleep(1)
    except:
        print("time out")        

sleep(5)
driver.close()
print(ctime())
```
 二）隐式等待   
 隐式等待是通过一定的时长等待页面上某元素加载完成。如果超出了设置的是时长元素还没有被加载，则抛出NoSuchElementException异常。WebDriver提供了implicitly_wait()方法来实现隐式等待，默认设置为0。它的用法相对来说要简单很多。

 
```
from selenium import webdriver
from selenium.common.exceptions import NoSuchElementException
from time import *

driver=webdriver.Firefox()
driver.get("https://www.baidu.com/")
driver.implicitly_wait(10)

try:
    print(ctime())
    element=driver.find_element_by_id("kw22").send_keys("selenium")
except NoSuchElementException as e:
    print(e)
finally:
    print(ctime())
    sleep(5)
    driver.quit()
```
 三）sleep休眠方法   
 sleep()方法用于 脚本在执行到某一位置时做固定时间的休眠，尤其是在脚本调试过程中。该方法由python的time模块提供。

 八、定位一组元素   
 WebDriver 还提供了与之对应的8 种定位方法用于定位一组元素。   
 find_elements_by_id()   
 find_elements_by_name()   
 find_elements_by_class_name()   
 find_elements_by_tag_name()   
 find_elements_by_link_text()   
 find_elements_by_partial_link_text()   
 find_elements_by_xpath()   
 find_elements_by_css_selector()   
 定位一组对象的方法与定位单个对象的方法类似，唯一的区别是在单词element 后面多了一个s 表示   
 复数。定位一组对象一般用于以下场景：   
 批量操作对象，比如将页面上所有的复选框都被勾选。   
 先获取一组对象，再在这组对象中过滤出需要具体定位的一些对象。比如定位出页面上所有的   
 checkbox，然后选择最后一个。

 
```
from selenium import webdriver
from time import *
import os

driver=webdriver.Firefox()
file_path='file:///'+os.path.abspath("checkbox.html")
driver.get(file_path)

sleep(2)
inputs=driver.find_elements_by_tag_name("input")

for i in inputs:
    if i.get_attribute("type")=="checkbox":
        i.click()
        sleep(2)
driver.quit()
```
 
```
from selenium import webdriver
from time import *
import os

driver=webdriver.Firefox()
file_path='file:///'+os.path.abspath("checkbox.html")
driver.get(file_path)

sleep(2)
checkboxs=driver.find_elements_by_xpath(".//*[@type='checkbox']")
#checkboxs=driver.find_elements_by_css_selector("input[type='checkbox']")

for checkbox in checkboxs:

        checkbox.click()
        sleep(2)

print(len(checkboxs))
checkboxs=driver.find_elements_by_css_selector("input[type='checkbox']").pop(0).click()
sleep(2)
driver.quit()
```
 九、多表单切换   
 Webdriver只能在一个页面上对元素识别与定位，对frame/iframe表单内嵌页面上的元素无法直接定位。需要通过switch_to.frame()方法将当前定位的主体切换为frame/iframe表单的内嵌页面。

 十、多窗口切换   
 Webdriver提供了switch_to.window()，可以实现在不同的窗口之间切换。

 
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from time import *

driver=webdriver.Chrome()
driver.get("https://www.baidu.com")
driver.implicitly_wait(10)

search_windows=driver.current_window_handle
driver.find_element_by_link_text("登录").click()
driver.find_element_by_link_text("立即注册").click()

all_handles=driver.window_handles

for handle in all_handles:
    if handle!=search_windows:
       driver.switch_to.window(handle)
       print("now register window!")
       driver.find_element_by_name("userName").send_keys("hahahaha")
       sleep(2)
for handle in all_handles:
    if handle==search_windows:
       driver.switch_to.window(handle)
       print("now search window!")
       driver.find_element_by_id("TANGRAM__PSP_4__closeBtn").click()
       driver.find_element_by_id("kw").send_keys("selenium2")
       driver.find_element_by_id("su").click()
       sleep(2)  

sleep(5)
driver.quit()
```
 十一、警告框处理   
 WebDriver中使用switch_to_alert（）方法定位alert/confiirm/prompt，然后使用text/accept/dismiss/send_keys等方法进行操作。   
 text：返回alert/confirm/prompt 中的文字信息   
 accept()：接受现有警告框   
 dismiss()：解散现有警告框   
 send_keys(keysToSend)：发送文本至警告框   
 keysToSend：将文本发送至警告框

 
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.action_chains import ActionChains
from time import *

driver=webdriver.Chrome()
driver.get("https://www.baidu.com")
driver.implicitly_wait(10)

link=driver.find_element_by_link_text("设置")
ActionChains(driver).move_to_element(link).perform()

driver.find_element_by_link_text("搜索设置").click()
sleep(10)
driver.find_element_by_link_text("保存设置").click()
sleep(5)

driver.switch_to_alert().accept()
sleep(5)
driver.quit()
```
 十二、上传文件   
 有两种方式：   
 1）通过form表单将这个值提交给服务器   
 2）插件上传：一般是指Flash、Javascript、Ajax等技术所实现的上传功能   
 对于input标签实现的上传功能，可以将其看作是一个输入框，即通过send_keys（）指定本地文件路径的方式实现文件上传。

 
```
from selenium import webdriver
import os
from time import *

driver=webdriver.Chrome()
file_path='file:///'+os.path.abspath('upfile.html')

driver.get(file_path)
driver.implicitly_wait(10)

driver.find_element_by_name("file").send_keys(r"C:\Users\Administrator\Desktop\jinggao.py")
sleep(10)
driver.quit()
```
 AutoIT实现上传

 
```
from selenium import webdriver
import os
from time import *

driver=webdriver.Chrome()
file_path='file:///'+os.path.abspath('upfile.html')

driver.get(file_path)
driver.implicitly_wait(10)

driver.find_element_by_name("file").click()

os.system(r"D:\upload.exe")
sleep(10)
driver.quit()
```
 十三、下载文件   
 为了让FireFox 浏览器能实现文件的下载，需要通过FirefoxProfile() 对其参数做一个设置。

 
```
from selenium import webdriver
from time import*
import os

fp=webdriver.FirefoxProfile()
fp.set_preference("brower.download.folderList",2)
fp.set_preference("browser.download.useDownloadDir","D:\\")
fp.set_preference("browser.helperApps.neverAsk.openFile","pplication/octet-stream")

sleep(5)
driver=webdriver.Firefox(firefox_profile=fp)
driver.get("https://pypi.org/project/selenium/")
driver.implicitly_wait(10)
driver.find_element_by_link_text("Download files").click()
driver.find_element_by_link_text("selenium-3.13.0.tar.gz").click()

sleep(5)
driver.quit()
```
 十四、操作Cookie   
 WebDriver 提供了操作Cookie 的相关方法可以读取、添加和删除cookie 信息。   
 webdriver操作cookie 的方法有：   
 get_cookies()— 获得所有cookie 信息   
 get_cookie(name)—返回有特定name 值有cookie 信息   
 add_cookie(cookie_dict)—-添加cookie，必须有name 和value 值   
 delete_cookie(name)—删除特定(部分)的cookie 信息   
 delete_all_cookies()—-删除所有cookie 信息

 
```
from selenium import webdriver
from time import *

driver=webdriver.Chrome()
driver.get("https://www.csdn.net/")

cookie=driver.get_cookies()

print(cookie)

sleep(5)
driver.quit()
```
 
```
from selenium import webdriver
from time import *

driver=webdriver.Chrome()
driver.get("https://www.csdn.net/")
driver.add_cookie({'name':'key-aaa','value':'value-aaaa'})
#cookie=driver.get_cookies()
for cookie in driver.get_cookies():
    print("%s->%s"%(cookie['name'],cookie['value']))

print(cookie)

sleep(5)
driver.quit()
```
   
  