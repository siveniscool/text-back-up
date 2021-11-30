---
title: butterfly主题记录
tag: 博客相关
category: 课外
cover: /imgs/feng2.jpg
---

# Butterfly主题记录

主要参考官方文档：https://butterfly.js.org/

## 碎碎念

​	就是对遇到的一些还记得的困难进行记录吧，，，

## 图片添加

​	因为之前重新配置了blog文件夹，所以要在根目录的`_config.yml`文件中将那个东西设置为ture。。。

​    在根目录`source`文件夹下加了一个imgs文件夹，在文章的title那里直接配置`cover: *.jpg`就可以

<font color='green'>突然意识到好像只记得这个,之后再加吧，反正看官方文档里还有很多功能。。。</font>



## 标签外挂

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





## Tabs

使用方法

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

{% tabs test1 %}
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



##### 自定义Tab名 + 只有icon + icon和Tab名

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



## Button

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

##### demo

```
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,,outline %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}
```

This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,,outline %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}

##### more than one button in center

```
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,pink larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,red larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,purple larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,orange larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,green larger %}

```

{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,pink larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,red larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,purple larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,orange larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,green larger %}

```
<div class="btn-center">
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline pink larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline red larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline purple larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline orange larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline green larger %}
</div>
```

<div class="btn-center">
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline pink larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline red larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline purple larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline orange larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline green larger %}
</div>
## label

<font color='green'>//可能是因为版本原因，这个好像暂时不能用，也可能是因为加了button之后就，不行了</font>



高亮文字

`{% label text color %}`

| 参数  |                             解释                             |
| ----- | :----------------------------------------------------------: |
| color | 【可选】背景颜色，默认为 default    default/blue/pink/red/purple/orange/green |
| text  |                             文字                             |



## 音乐

参考：https://butterfly.js.org/posts/507c070f/

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

参数解读看https://butterfly.js.org/posts/507c070f/#%E6%8F%92%E5%85%A5Aplayer-html

