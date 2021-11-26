---
title: send-email
date: 2021-11-23 20:56:25
tag: python
cover: /imgs/feng.jpg
---



## 发送邮件的步骤

1. 连接服务器
2. 通过账号和密码登录邮箱
3. 填写收件人
4. 填写主题
5. 填写正文
6. 发送邮件
7. 退出邮箱

## 过程

### 使用smtplib库连接服务器

```python
import smtplib
mailhost = 'smtp.qq.com' #把qq邮箱的服务器地址赋值到变量mailhost上
qqmail = smtplib.SMTP()  #实例化一个smtplib模块里的SMTP对象，这样就可以使用MSTP对象的方法和属性了
qqmail.connect(mailhost,25)  #连接服务器，第一个参数是服务器地址，第二个参数是SMTP的端口号
```

qq邮箱的服务器地址就是“smtp.qq.com”

### 通过账号和密码登录邮箱，填写收件人

```python
account = input("your email address")
password = input("your email password")
qqmail.login(account,password) #登录邮箱，第一个是邮箱的账号，第二个是邮箱的密码
receiver = input("receiver's email")  #收件人的邮箱
```

注意：password是开启了SMTP服务之后的授权妈妈

### 填写主题和正文

```python
from email.mime.text import MIMEText
from email.header import Header
content = input('your content:')
message = MIMEText(content, 'plain','utf-8') #实例化一个MIMEText对象，需要有正文、文本格式和编码三个参数
subject = input("your subject")
message['Subject'] = Header(subject,'utf-8') #再等号的右边是实例化了一个Header邮件头对象，需要写入两个参数，主题和编码，赋值给右边的message['Subject']
```

message['Subject']就是MIMEText类中的Subject属性名取到该属性

### 发送邮件和退出邮箱

```python
qqmail.sendmail(account,receiver,message.as_string()) #发送邮件，调用sendmail()方法，写入发件人，收件人和字符串格式的信息
qqmail.quit()
```

### 定时

选取第三方库`schedule`,需要安装。

```python
import schedule
import time

def job():
    ...
    
schedule.every(10).minutes.do(job)  #每十分钟执行一次job()函数的任务
schdule.every().day.at("10:30").do(job)  #部署每天的10：30执行一次job函数的任务

```
