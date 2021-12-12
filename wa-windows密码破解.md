---
title: windows密码破解
time: 2021/11/27 19:18:00
tag: wa
category: 学习笔记
cover: /imgs/feng8.jpg
---



windows密码破解 win7系统 and winxp系统

#### win7

1. 下载gethashes软件

![](image-20211127142435766.png)

2. 直接win+r打开软件，显示需要管理员权力

![image-20211127142842190](image-20211127142842190.png)

3. 打开telent服务

![image-20211127142932304](image-20211127142932304.png)4. 继续试试gethashes.exe,什么都没有发生

![image-20211127143519751](image-20211127143519751.png)5. 看了https://zhuanlan.zhihu.com/p/58709299

将gethashes.exe转到SAM文件在的那个路径下，关闭防火墙，使用命令，什么也没有发生

![image-20211127144512998](image-20211127144452765.png)

6. 看了https://blog.51cto.com/qlxmy/1675841

说是win7已经没办法找到了，只能是xp系统或者03系统（？？？你tm）

#### ![image-20211127144619685](image-20211127144619685.png)

#### 使用xp虚拟机

1. 开启telent服务

![image-20211127153049433](image-20211127153049433.png)添加文件2. 2. 使用gethashes.exe $Local,行了

![image-20211127154141272](image-20211127154141272.png)3. 复制粘贴哈希值，到网站，显示服务器故障

![image-20211127154805866](image-20211127154805866.png)过了一会又试了一下，行了

![image-20211127155426749](image-20211127155426749.png)10. SAM文件无法打开

![image-20211127155757365](image-20211127155733542.png)

![image-20211127155757365](image-20211127155757365.png)

累了 毁灭吧



add.

有软件可以破解win10的密码，法国某大佬搞的。但是目前已知的只有这个软件可以破win10的。。。。