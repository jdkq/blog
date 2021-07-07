---
title: butterfly3.0新功能
tags: butterfly
categories: hexo
description: butterfly标签外挂以及隐藏toggle
aplayer: false
abbrlink: 48907
date: 2020-09-07 01:23:56
keywords:
top_img:
comments:
cover:
sticky:
toc:
toc_number:
auto_open:
copyright:
copyright_author:
copyright_author_href:
copyright_url:
copyright_info:
mathjax:
katex:
highlight_shrink:
---
# 标签外挂

```
{% note default %}
default 提示块标籤
{% endnote %}

{% note primary no-icon %}
primary 提示块标籤
{% endnote %}

{% note success %}
success 提示块标籤
{% endnote %}

{% note info %}
info 提示块标籤
{% endnote %}

{% note warning %}
warning 提示块标籤
{% endnote %}

{% note danger %}
danger 提示块标籤
{% endnote %}
```

{% note default %}
default 提示块标籤
{% endnote %}

{% note primary no-icon %}
primary 提示块标籤
{% endnote %}

{% note success %}
success 提示块标籤
{% endnote %}

{% note info %}
info 提示块标籤
{% endnote %}

{% note warning %}
warning 提示块标籤
{% endnote %}

{% note danger %}
danger 提示块标籤
{% endnote %}


# Tag-hide

<hr>

* inline

```
{% hideInline content,display,bg,color %}
```

哪个英文字母最酷？ {% hideInline 因为西装裤(C装酷),查看答案,#FF7242,#fff %}

门里站着一个人? {% hideInline 闪 %}

<hr>

* block (可以隐藏图片代码块以及很多内容)

```
{% hideBlock display,bg,color %}
content
{% endhideBlock %}
```

查看答案
{% hideBlock 查看答案 %}
傻子，怎么可能有答案
{% endhideBlock %}

<hr>

* toggle

```
{% hideToggle display,bg,color %}
content
{% endhideToggle %}
```

{% hideToggle Butterfly安装方法 %}
在你的博客根目录里

git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly

如果想要安装比较新的dev分支，可以

git clone -b dev https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly

{% endhideToggle %}


# Tabs

1. 默认

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

<hr>

2. 预选第三个

```
{% tabs test2, 3 %}
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
```
{% tabs test2, 3 %}
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

<hr>

3. 没有预选值

```
{% tabs test3, -1 %}
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
```
{% tabs test3, -1 %}
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

<hr>

4. 自定义 Tab 名 + 只有 icon + icon 和 Tab 名

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


# Button

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
```
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,blue larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,pink larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,red larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,purple larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,orange larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,green larger %}
```
{% btn 'https://asdsa.top',what,far fa-hand-point-right,larger %}
{% btn 'https://asdsa.top',what,far fa-hand-point-right,blue larger %}
{% btn 'https://asdsa.top',what,far fa-hand-point-right,pink larger %}
{% btn 'https://asdsa.top',what,far fa-hand-point-right,red larger %}
{% btn 'https://asdsa.top',what,far fa-hand-point-right,purple larger %}
{% btn 'https://asdsa.top',what,far fa-hand-point-right,orange larger %}
{% btn 'https://asdsa.top',what,far fa-hand-point-right,green larger %}

```
<div class="btn-center">
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline blue larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline pink larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline red larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline purple larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline orange larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline green larger %}
</div>
```
<div class="btn-center">
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline blue larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline pink larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline red larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline purple larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline orange larger %}
{% btn 'http://www.jerryc.me',JerryC,far fa-hand-point-right,outline green larger %}
</div>