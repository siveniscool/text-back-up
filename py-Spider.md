---
title: Spider
date: 2021-11-20 10:18:59
tags: python
description: 因为划了很久的水，所以大概都忘光了。。。
cover: /imgs/feng.jpg
---



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

#### 带参数的请求数据

1. 从XHR中找到需要的数据，将`Query String Parameters`里的内容封装为一个字典，传递给 **params**（params是requests.get()中的一个参数）
2. 添加**Request Headers**,可以使用Requests，哦快的官方文档中“user-agent”来看。`origin`或`refer`也类似
3. 然后将他们放在requests.get()的参数中

#### cookies

> 有时需要登录才能访问一些网址

<font color='green'>//此处插一条关于网页访问的方法的内容，但是先略一下</font>

* cookies通常在response headers中
* 有关登录的参数，还有from data中的参数

为了避免被反爬虫，要在requests.post()的参数中加上data参数，可以相当于成功登录

* 提取cookies的方法，调用requests对象的cookies属性获得登录的cookies

```python
log_in = requests.post(url,headers=headers,data=data)
cookies = log_in.cookies
```

#### 存储cookies



#### session

> session就是会话过程中，服务器用来记录特定用户会话的信息，cookies中还存储这session的编码信息，session中也存储着cookies的信息

因为ression和cookies的关系，我们可以创建session来处理cookies

使用方法

```pyt
session.post(url,headers=headers,data=data)
```



### 存储在json中的数据

> 当爬取网页源代码时发现需要的数据不在源代码中，就需要通过network来寻找数据

json相当于一个字典和列表的组合体

就像

```python
c = {
    'a':
    [
        {'a':'b','c':'d'}
    ]
}
```

将request到的数据变成json对象，可以使用

```python
a = requests.get(url)
b = a.json()
```

然后一层一层的取字典，就可以获得一个列表，再取列表里的元素，就可以得到想要的数据

```python
c = b['a']['b']
for i in c:
    d = i["data's name"]
```





## 数据解析

> 主要使用的是BeautifulSoup库

使用方法

```python
bs对象 = BeautifulSoup（要解析的文本，'解析器'）
```

* 第一个参数‘要解析的文本’必须是字符串
* ‘解析器’使用的一般是一个python的内置库：html.parser

## 提取数据

> 使用find()和find_all()匹配html的标签和属性，再使用tag对象的方法提取内容

👉**tag对象的三种用法**

首先要明确，使用Beautiful库提取出来的内容就是tag对象

* tag.find()和tag.find_all()       提取tag中的tag
* tag.text                                   提取tag中的文字
* tag['属性名']                           提取tag中这个属性的值

