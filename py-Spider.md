---
title: Spider
date: 2021-11-20 10:18:59
tags: python
description: 因为划了很久的水，所以大概都忘光了。。。
cover: /imgs/feng.jpg
---

# 

## 基本工作步骤

1. 获取数据。根据提供的网址，向服务器发起请求，然后返回数据
2. 解析数据。把服务器返回的数据解析成我们能读懂的格式
3. 提取数据。从中提取我们需要的数据
4. 存储数据。把有用的数据存储起来

## robots协议

> 看会不会被抓啥的

`url/robots.txt`

就能看到了

## 获取数据

>  使用resquests库

### request.get()

request.get()返回的是一个`Response`类的对象

👉**Response常用属性**

```html
response.status_code				//检查请求是否成功

response.content					//把response对象转换为二进制数据

response.text						//把response对象转换为字符串数据

response.enconding				    //定义response对象的编码
```

* response.status_code，可以用来检查请求是否正确响应
  * 200 服务器同意请求
  * 1** 服务器收到请求，如100，继续提出请求
  * 2** 请求成功，如200，请求成功
  * 3** 重定向，如305，应使用代理访问
  * 4** 客户端错误 ，如403，禁止访问
  * 5** 服务器端错误，如503，服务不可用
* response.content,适用于图片、音频和视频的下载

```python
pic = h_pic.content
pho = open file('a.jpg','wb')
pho.write(pic)
pho.close()
```



* response.text，适用于文字，网页源代码的下载

```python
novel = html.text
#这时的novel就是字符串格式，可以写入文件
```

* response.encoding,可以定义Response对象的编码，遇到文本乱码的情况才考虑用这个

`response.encoding = 'gbk'  #就是将返回的数据用gbk编码`

## 数据解析

