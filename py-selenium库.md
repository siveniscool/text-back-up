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

   `driver = webdriver.Chrome()`#就是将引擎设置为Chrome，打开一个Chrome浏览器

2. 获取那个网址

   ​	driver.get(url)	

   > 这里的url如果是ip地址的话，可以用`http://ip`的方式来写

3. 