---
title: 云服务器搭建记录
date: 2021-12-01 19:14:26
tags: web
description: 记录一下从负数开始研究linux云服务器的惨痛经历
category: 学习笔记
cover: /imgs/feng6.jpg

---

{% hideToggle 碎碎念, blue %}

因为之前就很想自己搭建一个网站，部署一下，放自己的图片啊文章啊什么的。直到有一天看到了阿里云学生便宜的云服务器，于是就去看了，结果发现，可以白嫖。。。于是白嫖了两周的Linux服务器，Linux云服务器比其他系统的要稳定，但是它的缺点也是显而易见的，那就是——我不会用。于是就开始各种摸爬滚打，目前进度：vsftpd安了，FTP搞了。但是，传不了文件，也就是不能从我的电脑主机传文件到云服务器。就，离谱。不过经历多了就好了。。。

{% endhideToggle %}

{% hideToggle 惨痛经历, blue %}

1. 阿里云

登录了阿里云，看到了学生服务器，看到了免费体验，于是就上了，甚至觉得：不就是Linux吗，学学就行了。于是，看到纯纯的黑纸白字的时候，我懵了两秒。。。

---

20211206

重整旗鼓，重新开始整吧。。。

1. 下载Xshell来连接远程的云服务器

2. 使用`yum install nginx`

3. 安装nginx，是一个服务器软件，用来使服务器可以在网页上被访问到![image-20211206203422148](image-20211206203422148.png)

   ![image-20211206203459937](image-20211206203459937.png)

4. 输入`nginx`启动服务器![image-20211206203541850](image-20211206203541850.png)

5. 安装宝塔这个软件，可以很方便的使用图形化面板来操作LNMP的东西们。

6. 发现好像不太行（可能是端口没打开）

7. 于是看了阿里云自带的教程

8. 先重新装一下操作系统

9. 先看看有没有ssh -V

10. 输入`ssh root@ip`和`yes`

11. 在ECS服务器上安装Apache服务及其扩展`yum -y install httpd httpd-manual mod_ssl mod_perl mod_auth_mysql`

12. 安装时遇到了问题

![image-20211206212509458](image-20211206212509458.png)

https://zhuanlan.zhihu.com/p/391850495

但是还是解决不了。。。整不动了，先去洗个澡。。。

好的洗完澡了。现在稍微理一理。。。

这次的服务器的版本时centOS8.4 *64，估计上面的那个是因为版本升级了所以会显示错误。那如果换一个版本呢？

所以试一试换一个版本吧。。

于是换成了centOS7.2 *64

1. 连接Xshell![image-20211206224841651](image-20211206224841651.png)
2. 安装apache，行了（😅）![image-20211206224954515](image-20211206224954515.png)
3. https://blog.51cto.com/u_13525470/2070375 关于安装apache之后打开浏览器还是看不到的问题。还是不行
4. 于是去看了https://how2j.cn/k/deploy2linux/deploy2linux-install/1600.html
5. 安装vsfptd
6. 不知道为什么他又可以了
7. 那就继续
8. 安装MySQL![image-20211206233323476](image-20211206233323476.png)
9. 安装php![image-20211206234430338](image-20211206234430338.png)
10. 安装和配置WordPress

---20211207---

1. 然后现在的进度是。apache，WordPress都有了。昨天研究了WordPress的主题什么的。发现，为什么我的WordPress是英文的，但是其他人的是中文的啊。
2. 于是好像需要用ftp什么的传输一下wordpress的安装包。。。
3. 于是又回到了ftp，之前看到了说有sftp的，今天试试？
4. 使用filezilla连接到远程云服务器![image-20211207103946168](image-20211207103946168.png)
5. 传输了wordpress![image-20211207105332733](image-20211207105332733.png)
6. 打开Xshell发现在了![image-20211207105623611](image-20211207105623611.png)
7. 历史性的突破！！！！！！欢呼！！！！
8. 然后就是怎么让wordpress显示在浏览器界面的问题
9. 首先新建了一个数据库https://zhuanlan.zhihu.com/p/318444530

![image-20211207110518086](image-20211207110518086.png)

10. 好像没能将apache的根目录转移到wordpress上。吃完饭再来看吧。

---

20211208

于是又开始了。

1. 先梳理一下。
2. 云服务器安装那四个东西，搞定了。可以使用Xshell来连接云服务器。wordpress已经传到了云服务器上面。现在的问题就是，怎么把apache的路径定到wordpress上面。。
3. 首先确定WordPress所在的目录是：/home/wwwroot/wordpress
4. 现在要修改wordpress中wp-config.php的指向路径
5. ？![image-20211208192352214](image-20211208192352214.png)
6. 好吧。重新传一次。。。
7. 然后照理来说，就是修改一下指向路径为绝对路径，然后把WordPress移动到apache的根目录，然后修改wp-config.php的配置文件，修改database_name_here，username_here,password_here为之前创建的数据库的内容，然后重启apache服务
8. 可是为什么查看目录的时候看不到嘞？
9. ![image-20211208193446977](image-20211208193446977.png)
10. 行，有了，那现在，开始改一改它的路径

![image-20211208193641332](image-20211208193641332.png)

11. 改了之后重启了appache

![image-20211208194228134](image-20211208194228134.png)

12. ![image-20211208194648493](image-20211208194648493.png)牛🙃
13. 好的那么现在更新一下php
14. ![image-20211208200650260](image-20211208200650260.png)
15. ![image-20211208200654655](image-20211208200654655.png)很好，问题变了。说明努力还是有用的
16. https://blog.csdn.net/weixin_42515376/article/details/114018165
17. 搞不定，因为下载的哪个WordPress需要php5.6.8以上的，但是安装了php70w（？）之后不能安装mysql，而且安装的mysql是mysqlend，名字不一样。。。好像需要改一下php的哪个文件。。。
18. 所以回到宝塔，看看能不能行？
19. 好的直接试试宝塔的哪个。。。
20. 哦要打开端口8888还是888
21. 记得密码是大写的https://blog.csdn.net/colorfulyan/article/details/108713410
22. 给您跪下了orz
23. ok下一步就是，怎么自定义网站了（估计是有前端的内容了。。）
24. 先这样

{% endhideToggle %}

搞完之后发现，还是hexo好用