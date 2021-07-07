---
title: Ubuntu使用dpkh安装依赖问题
categories: 操作系统
tags: dpkg依赖
top_img: >-
  https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1198978613,2079001128&fm=26&gp=0.jpg
cover: >-
  https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3256004829,2623044380&fm=26&gp=0.jpg
abbrlink: 56522
date: 2020-03-27 21:17:19
comments:
hide:
toc:
---
<blockquote>
Ubuntu使用dpkg安装软件依赖问题解决
</blockquote>
这里以在ubuntu 16.04安装Ubuntu Tweak为例进行说明，通常安装包依赖问题都可以用这种方法解决：
{%codeblock%}
sudo apt-get install -f
{%endcodeblock%}
也要善用update等。