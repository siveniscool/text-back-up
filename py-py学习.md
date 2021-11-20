---
title: PY学习笔记
tag: python
cover: /imgs/feng.jpg
---

### Network

  主要是因为有时网页源代码里并么有需要的信息，所以需要在Network中找到需要的信息。

#### network的功能

  记录当前页面上发生的所有请求。

#### XHR

  XHR是Network中一种比较重要的请求。也就是在实现新增页面但是不改变网址的功能时，需要使用一种明教Ajax的技术，在这种技术工作的时候，会首先搭建一个XHR对象，用这个XHR对象来实现服务器和浏览器的数据传输。这里的XHR和Fetch差不多，只不过Fetch出现的晚一些。

#### json

  是一种数据交换的语法，有点像是字典和列表的结合体

```
//定义一个json
a = {
       'thisa':
       [
           {"name":"a","num":"b"},
           {"name":"c","num":"d"}
       ]
     }
```

接上文，XHR的存储格式就是json

#### 具体操作

1. 检查，找到network，勾选`Preserve log`

2. 勾选XHR，依次查找文件

3. 在general中看到了requesturl，此时访问的网址就是`RequestUrl`的网址

4. 在得到response之后，使用a.json()的方法将json转为列表/字典

5. 然后一层一层的取字典（`a[b][c]`）

6. 然后一层一层取列表

   ```
   for i in list:
   							print(a[b])
   ```

 