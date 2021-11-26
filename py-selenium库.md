---
title: selenium库
tag: python
cover: /imgs/feng.jpg
---

### selenium库

  首先这个库是干啥的来着。这个可以模拟人控制浏览器，做出自动打开、输入、点击等操作。



### 使用

在使用selenium库之前，先要安装浏览器驱动https://localprod.pandateacher.com/python-manuscript/crawler-html/chromedriver/ChromeDriver.html

> 期间有个问题就是，需要下载一个和自己的chrome浏览器相配的版本，然后安装到自己python文件夹的scrip（？好像不是这么拼的。。）文件夹下



1. 设置浏览器引擎

```python
from selenium import webdriver
driver = webdriver.Chrome()#就是将引擎设置为Chrome，打开一个Chrome浏览器
```

2. 获取那个网址

​	driver.get(url)	

可以用来打开制定的url网页

`driver.close()`

用来关闭浏览器的驱动

> 这里的url如果是ip地址的话，可以用`http://ip`的方式来写

3. 解析数据与提取数据

用selenium打开网页之后，就将所有的信息加载到了elements里，之后就可以把动态网页用静态网页的方法提取了。具体代码是

```python
label = driver.find_element_by_tag_name('label')
#还有其他查找元素的方法
find_element_by_class_name
find_element_by_id
find_element_by_name
find_element_by_link_text #通过连接文本获取超链接
```

提取出的数据是webelement类对象，这类对象也有一个.text的属性，或者使用`WebElement.get_attribute()`的方法输入参数提取属性值

3.1. 还可以用selenium获取网页，然后用beautifulsoup来解析和提取，如果要获取网页的源代码。可以使用

`html = driver.opage_source`

4. 模拟按键输入和点击元素

```python
.send_keys()  #用来模拟按键输入，自动填写表单
.click()  #点击元素
.clear()  #用来清除元素的内容

```

