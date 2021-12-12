---
title: Butterfly主题参考记录
tag: 博客相关
category: 博客
description: 为了防止自己忘了该怎么写，记录一下
cover: /imgs/feng2.jpg
---

# Butterfly主题记录

主要参考官方文档：https://siveniscool.com.cn/

{% hideToggle 碎碎念, grey %}

发现有很多可操作的东西，但是因为太多了所以总是看过之后就忘了在哪里。。。

{% endhideToggle %}

## 图片添加

​	因为之前重新配置了blog文件夹，所以要在根目录的`_config.yml`文件中将那个东西设置为ture。。。

​    在根目录`source`文件夹下加了一个imgs文件夹，在文章的title那里直接配置`cover: *.jpg`就可以

<font color='green'>突然意识到好像只记得这个,之后再加吧，反正看官方文档里还有很多功能。。。</font>

<br>

## 首页置顶图轮播

https://akilar.top/posts/8e1264d1/

<br>

## 标签外挂

### 📍Tabs

**使用方法**

```
{% tabs Unique name, [index] %}
<!-- tab [Tab caption] [@icon] -->
Any content (support inline tags too).
<!-- endtab -->
{% endtabs %}

Unique name   : Unique name of tabs block tag without comma.
                Will be used in #id's as prefix for each tab with their index numbers.
                If there are whitespaces in name, for generate #id all whitespaces will replaced by dashes.
                Only for current url of post/page must be unique!
[index]       : Index number of active tab.
                If not specified, first tab (1) will be selected.
                If index is -1, no tab will be selected. It's will be something like spoiler.
                Optional parameter.
[Tab caption] : Caption of current tab.
                If not caption specified, unique name with tab index suffix will be used as caption of tab.
                If not caption specified, but specified icon, caption will empty.
                Optional parameter.
[@icon]       : FontAwesome icon name (full-name, look like 'fas fa-font')
                Can be specified with or without space; e.g. 'Tab caption @icon' similar to 'Tab caption@icon'.
                Optional parameter.
```

{% tabs test1, -1 %}
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}



##### 自定义Tab名 ; 只有icon +;icon和Tab名

```
{% tabs test4 %}
<!-- tab 第一个Tab -->
**tab名字为第一个Tab**
<!-- endtab -->

<!-- tab @fab fa-apple-pay -->
**只有图标 没有Tab名字**
<!-- endtab -->

<!-- tab 炸弹@fas fa-bomb -->
**名字+icon**
<!-- endtab -->
{% endtabs %}

```

{% tabs test4 %}
<!-- tab 第一个Tab -->
**tab名字为第一个Tab**
<!-- endtab -->

<!-- tab @fab fa-apple-pay -->
**只有图标 没有Tab名字**
<!-- endtab -->

<!-- tab 炸弹@fas fa-bomb -->
**名字+icon**
<!-- endtab -->
{% endtabs %}



### 📍note

#### 正常的note

{% tabs 1, -1 %}

<!-- tab markdown中的源码 -->

```{% note simple %}
{% note simple %}
默认 提示块标籤
{% endnote %}

{% note default simple %}
default 提示块标籤
{% endnote %}

{% note primary simple %}
primary 提示块标籤
{% endnote %}

{% note success simple %}
success 提示块标籤
{% endnote %}

{% note info simple %}
info 提示块标籤
{% endnote %}

{% note warning simple %}
warning 提示块标籤
{% endnote %}

{% note danger simple %}
danger 提示块标籤
{% endnote %}

```

<!-- endtab -->

<!-- tab 展示 -->

{% note simple %}
默认 提示块标籤
{% endnote %}

{% note default simple %}
default 提示块标籤
{% endnote %}

{% note primary simple %}
primary 提示块标籤
{% endnote %}

{% note success simple %}
success 提示块标籤
{% endnote %}

{% note info simple %}
info 提示块标籤
{% endnote %}

{% note warning simple %}
warning 提示块标籤
{% endnote %}

{% note danger simple %}
danger 提示块标籤
{% endnote %}

<!-- endtab -->

<!-- tab 自定义note,源码 -->

```
{% note 'fab fa-cc-visa' simple %}
你是刷 Visa 還是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' simple %}
2021年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' simple %}
小心開車 安全至上
{% endnote %}
{% note red 'fas fa-fan' simple%}
這是三片呢？還是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' simple %}
你是刷 Visa 還是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' simple %}
剪刀石頭布
{% endnote %}
{% note green 'fab fa-internet-explorer' simple %}
前端最討厭的瀏覽器
{% endnote %}
```

<!-- endtab -->

<!-- tab 展示2 -->

{% note 'fab fa-cc-visa' simple %}
你是刷 Visa 還是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' simple %}
2021年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' simple %}
小心開車 安全至上
{% endnote %}
{% note red 'fas fa-fan' simple%}
這是三片呢？還是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' simple %}
你是刷 Visa 還是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' simple %}
剪刀石頭布
{% endnote %}
{% note green 'fab fa-internet-explorer' simple %}
前端最討厭的瀏覽器
{% endnote %}

<!-- endtab -->

{% endtabs %}

#### 上标的note

{% tabs 2, -1 %}

<!-- tab 展示 -->

{% tip %}默认情况{% endtip %}
{% tip success %}success{% endtip %}
{% tip error %}error{% endtip %}
{% tip warning %}warning{% endtip %}
{% tip bolt %}bolt{% endtip %}
{% tip ban %}ban{% endtip %}
{% tip home %}home{% endtip %}
{% tip sync %}sync{% endtip %}
{% tip cogs %}cogs{% endtip %}
{% tip key %}key{% endtip %}
{% tip bell %}bell{% endtip %}
{% tip fa-atom %}自定义font awesome图标{% endtip %}

<!-- endtab -->

<!-- tab markdown中的源码 -->

```
{% tip [参数，可选] %}文本内容{% endtip %}
样式: success,error,warning,bolt,ban,home,sync,cogs,key,bell
自定义图标: 支持fontawesome。

{% tip %}默认情况{% endtip %}
{% tip success %}success{% endtip %}
{% tip error %}error{% endtip %}
{% tip warning %}warning{% endtip %}
{% tip bolt %}bolt{% endtip %}
{% tip ban %}ban{% endtip %}
{% tip home %}home{% endtip %}
{% tip sync %}sync{% endtip %}
{% tip cogs %}cogs{% endtip %}
{% tip key %}key{% endtip %}
{% tip bell %}bell{% endtip %}
{% tip fa-atom %}自定义font awesome图标{% endtip %}
```

<!-- endtab -->

{% endtabs %}

#### 动态的note

```
{% tip [参数，可选] %}文本内容{% endtip %}
```

啊好麻烦懒得搞了

<br>

### 📍Button

#### 一般的款式

{% tabs 3, -1 %}

<!-- tab 使用方法 -->

```
{% btn [url],[text],[icon],[color] [style] [layout] [position] [size] %}

[url]         : 链接
[text]        : 按钮文字
[icon]        : [可选] 图标
[color]       : [可选] 按钮背景顔色(默认style时）
                      按钮字体和边框顔色(outline时)
                      default/blue/pink/red/purple/orange/green
[style]       : [可选] 按钮样式 默认实心
                      outline/留空
[layout]      : [可选] 按钮佈局 默认为line
                      block/留空
[position]    : [可选] 按钮位置 前提是设置了layout为block 默认为左边
                      center/right/留空
[size]        : [可选] 按钮大小
                      larger/留空
```

<!-- endtab -->

<!-- tab demo -->

```
正常的一般通过button {% btn 'https://siveniscool.com.cn/',siven %}
有标记的button {% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right %}
没有填充的button {% btn 'https://siveniscool.com.cn/',siven,outline %}
没有填充有标记的button {% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline %}
大一点的button {% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,larger %}
```

正常的一般通过button {% btn 'https://siveniscool.com.cn/',siven %}
有标记的button {% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right %}
没有填充的button {% btn 'https://siveniscool.com.cn/',siven,outline %}
没有填充有标记的button {% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline %}
大一点的button {% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,larger %}

##### 有颜色的button

```
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,blue larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,pink larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,red larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,purple larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,orange larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,green larger %}

```

{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,blue larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,pink larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,red larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,purple larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,orange larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,green larger %}

##### 有颜色的button，没有填充。而且居中

```
<div class="btn-center">
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline blue larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline pink larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline red larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline purple larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline orange larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline green larger %}
</div>
```

<div class="btn-center">
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline blue larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline pink larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline red larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline purple larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline orange larger %}
{% btn 'https://siveniscool.com.cn/',siven,far fa-hand-point-right,outline green larger %}
</div>

<!-- endtab -->

{% endtabs %}

#### 进阶的款式

{% tabs 4, -1 %}

<!-- tab 源码 -->

```markdown
{% btns 样式参数 %}
{% cell 标题, 链接, 图片或者图标 %}
{% cell 标题, 链接, 图片或者图标 %}
{% endbtns %}
```

参数配置

{% radio blue, 圆角样式：rounded，circle %}

{% radio blue, 增加文字样式：可以在文字中增加`<b>标题样式</b>`，和`<p>描述文字</p>` %}

{% radio blue, 还有布局方式，反正就很麻烦 %}

<!-- endtab -->

<!-- tab 展示 -->

{% btns circle grid5 %}
{% cell xaoxuu, https://xaoxuu.com, https://cdn.jsdelivr.net/gh/xaoxuu/cdn-assets/avatar/avatar.png %}
{% cell xaoxuu, https://xaoxuu.com, https://cdn.jsdelivr.net/gh/xaoxuu/cdn-assets/avatar/avatar.png %}
{% cell xaoxuu, https://xaoxuu.com, https://cdn.jsdelivr.net/gh/xaoxuu/cdn-assets/avatar/avatar.png %}
{% cell xaoxuu, https://xaoxuu.com, https://cdn.jsdelivr.net/gh/xaoxuu/cdn-assets/avatar/avatar.png %}
{% cell xaoxuu, https://xaoxuu.com, https://cdn.jsdelivr.net/gh/xaoxuu/cdn-assets/avatar/avatar.png %}
{% endbtns %}

<!-- endtab -->

{% endtabs %}

#### 隐藏内容

```markdown
{% hideInline content,display,bg,color %}

{% hideBlock display,bg,color %}
content
{% endhideBlock %}
```

- content: 文本内容
- display: 按钮显示的文字 (可选)
- bg: 按钮的背景颜色 (可选)
- color: 按钮文字的颜色 (可选)

如：

```
{% hideInline clicked, click, \#7AC5CD, #FFFAFA %}

{% hideBlock 这是隐藏的内容, \#7AC5CD, #FFFAFA %}

content

{% endhideBlock %}
```



{% hideInline clicked, click, \#7AC5CD, #FFFAFA %}

<br>

{% hideBlock 这是隐藏的内容, \#7AC5CD, #FFFAFA %}

content

{% endhideBlock %}

<br>

### 📍label

高亮文字

`{% label text color %}`

| 参数  |                             解释                             |
| ----- | :----------------------------------------------------------: |
| color | 【可选】背景颜色，默认为 default    default/blue/pink/red/purple/orange/green |
| text  |                             文字                             |

如 {% label text blue %}

更多小标签见https://www.antmoe.com/posts/3b43914f/#%E8%A1%8C%E5%86%85%E5%B0%8F%E6%A0%87%E7%AD%BE

<br>

## 文本样式

#### 行内文本样式 text

{% tabs tabs, -1 %}

<!-- tab 展示 -->

这是{% u 带下划线的文本 %}
这是{% emp 带着重号的文本 %}
这是{% wavy 带波浪线的文本 %}
这是{% del 带删除线的文本 %}
这是{% kbd 带键盘样式的文本 %}
这是{% psw 带密码样式的文本 %}

<!-- endtab -->

<!-- tab 源码 -->

```
这是{% u 带下划线的文本 %}
这是{% emp 带着重号的文本 %}
这是{% wavy 带波浪线的文本 %}
这是{% del 带删除线的文本 %}
这是{% kbd 带键盘样式的文本 %}
这是{% psw 带密码样式的文本 %}
```

<!-- endtab -->

{% endtabs %}

#### 行内文本样式 span

{% tabs 5,-1 %}

<!-- tab 展示 -->

- 彩色文字
在一段话中方便插入各种颜色的标签，包括：{% span red, 红色 %}、{% span yellow, 黄色 %}、{% span green, 绿色 %}、{% span cyan, 青色 %}、{% span blue, 蓝色 %}、{% span gray, 灰色 %}。
- 超大号文字
文档「开始」页面中的标题部分就是超大号文字。
{% span center logo large, Volantis %}
{% span center small, A Wonderful Theme for Hexo %}

<!-- endtab -->

<!-- tab markdown中的文本 -->

```markdown
{% span 样式参数(参数以空格划分), 文本内容 %}
字体: logo, code
颜色: red,yellow,green,cyan,blue,gray
大小: small, h4, h3, h2, h1, large, huge, ultra
对齐方向: left, center, right

- 彩色文字
在一段话中方便插入各种颜色的标签，包括：{% span red, 红色 %}、{% span yellow, 黄色 %}、{% span green, 绿色 %}、{% span cyan, 青色 %}、{% span blue, 蓝色 %}、{% span gray, 灰色 %}。
- 超大号文字
文档「开始」页面中的标题部分就是超大号文字。
{% span center logo large, Volantis %}
{% span center small, A Wonderful Theme for Hexo %}
```

<!-- endtab -->

{% endtabs %}

#### 复选列表 checkbox

{% tabs fuxuan, -1 %}

<!-- tab 源码 -->

```
{% checkbox 样式参数,文本 %}
```

1. 样式: plus, minus, times
2. 颜色: red,yellow,green,cyan,blue,gray
3. 选中状态: checked

```
{% checkbox 纯文本测试 %}
{% checkbox checked, 支持简单的 [markdown](https://guides.github.com/features/mastering-markdown/) 语法 %}
{% checkbox red, 支持自定义颜色 %}
{% checkbox green checked, 绿色 + 默认选中 %}
{% checkbox yellow checked, 黄色 + 默认选中 %}
{% checkbox cyan checked, 青色 + 默认选中 %}
{% checkbox blue checked, 蓝色 + 默认选中 %}
{% checkbox plus green checked, 增加 %}
{% checkbox minus yellow checked, 减少 %}
{% checkbox times red checked, 叉 %}
```



<!-- endtab -->

<!-- tab 样式预览 -->

{% checkbox 纯文本测试 %} {% checkbox checked, 支持简单的 [markdown](https://guides.github.com/features/mastering-markdown/) 语法 %} {% checkbox red, 支持自定义颜色 %} {% checkbox green checked, 绿色 + 默认选中 %} {% checkbox yellow checked, 黄色 + 默认选中 %} {% checkbox cyan checked, 青色 + 默认选中 %} {% checkbox blue checked, 蓝色 + 默认选中 %} {% checkbox plus green checked, 增加 %} {% checkbox minus yellow checked, 减少 %} {% checkbox times red checked, 叉 %}

<!-- endtab -->

{% endtabs %}

看https://akilar.top/posts/615e2dec/

<br>

## 音乐

参考：https://siveniscool.com.cn/posts/507c070f/

​           https://blog.csdn.net/hushhw/article/details/88092728

1. 首先是安装那个插件

`npm install --save hexo-tag-aplayer`

2. 在hexo的配置文件_config.yml中设置

`aplayer:`

​    `meting: ture`

3. 在hexo的配置文件中设置

`aplayer:`

​    `asset_injext: false`

4. 在主题的配置文件中

```YML
# Inject the css and script (aplayer/meting)
aplayerInject:
  enable: true
  per_page: true
```



5. 新建文件`/layout/_partial/aplayer.pug`,写

```PUG
link(rel="stylesheet" type='text/css', href="https://cdn.jsdelivr.net/npm/aplayer@1.10/dist/APlayer.min.css")
script(type='text/javascript', src="https://cdn.jsdelivr.net/npm/aplayer@1.10/dist/APlayer.min.js")
script(type='text/javascript', src="https://cdn.jsdelivr.net/npm/meting@1.2/dist/Meting.min.js")

```

6. 然后在主题的配置文件中？插入Aplayer html

```MARKDOWN
# Inject
# Insert the code to head (before '</head>' tag) and the bottom (before '</body>' tag)
# 插入代码到头部 </head> 之前 和 底部 </body> 之前
inject:
  head:
     - <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sviptzk/HexoStaticFile@latest/Hexo/js/mouse_snow.min.js">
  bottom:
    - <div class="aplayer no-destroy" data-id="1867077039" data-server="netease" data-type="song" data-fixed="true" data-mini="true" data-listFolded="false" data-order="random" data-preload="none" data-autoplay="true" muted></div>
```

参数解读看https://siveniscool.com.cn/posts/507c070f/#%E6%8F%92%E5%85%A5Aplayer-html

#### 添加音频文件

。。。找不到了，找到再说把。。。

<br>

## 时间线

```
{% timeline 时间线标题 %}
{% timenode 时间节点（标题） %}
content
{% endtimenode %}
{% timenode 时间节点（标题） %}
content
...
{% endtimeline %}
```



## 导航栏新添元素

我真傻，真的。config.yml里直接改，在source文件夹中加就行了。

那么目前想要实现的：

1. 图库  就是在那个index文件夹里面加如Gallery的那个

2. 追番  但是好麻烦啊。算了算了

3. 友链动态  也是看起来很麻烦。待定

   ...

## live2d看板娘

算了，不会搞。https://mx.paul.ren/course

https://akilar.top/posts/5b8f515f/

更多

https://akilar.top/posts/23fdf850/