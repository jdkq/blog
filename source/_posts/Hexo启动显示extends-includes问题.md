---
title: Hexo启动显示extends includes问题
top_img: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586373395944&di=b6d32eb2b7445bf05a988cd60a68dfe0&imgtype=0&src=http%3A%2F%2Fpic2.zhimg.com%2Fv2-f9654b817205f6af3e472af284ecc2b2_1200x500.jpg
cover: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586373344338&di=8256142b9bdc2e8baca320082180636b&imgtype=0&src=http%3A%2F%2Fpic1.zhimg.com%2Fv2-ea09f654adbdb18f7d3b31577ee49557_t.jpg
tags: hexo 切换系统出现的问题
categories: hexo
abbrlink: 22293
date: 2020-04-08 00:58:54
comments:
hide:
toc:
---
> Hexo更改主题后启动服务器，界面显如下字符:

`extends includes/layout.pug block content include includes/recent-posts.pug include includes/partial`

## 解决方案
**执行如下命令**
```bash
npm install --save hexo-renderer-jade hexo-generator-feed hexo-generator-sitemap hexo-browsersync hexo-generator-archive
```
**清除缓存**
`hexo clean`

**生成静态文件**
`hexo g`

![tp](https://img-blog.csdnimg.cn/20200315200855784.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMxODgzMA==,size_16,color_FFFFFF,t_70)
