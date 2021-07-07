---
title: NEXT-Hexo
categories: hexo
tags: Next主题
author: dong
top_img: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586260330756&di=d6ac44abd6c3cc474ddf86b79c8a81b9&imgtype=0&src=http%3A%2F%2Fpic2.zhimg.com%2Fv2-f9654b817205f6af3e472af284ecc2b2_1200x500.jpg
cover: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586260443421&di=d74364e82958a98bfe2cd041e9d70829&imgtype=0&src=http%3A%2F%2Fupload.techweb.com.cn%2Fs%2F640%2F2020%2F0407%2F1586231350427.jpg
abbrlink: 10404
date: 2020-03-13 12:43:00
comments:
hide:
toc:
---
## 主题使用教程
<blockquote>
	Hexo 是高效的静态站点生成框架，它基于 *Node.js* 。 通过 Hexo 你可以轻松地使用 Markdown 编写文章，除了 Markdown 本身的语法之外，还可以使用 Hexo 提供的 标签插件 来快速的插入特定形式的内容。在这篇文章中，假定你已经成功安装了 Hexo，并使用 Hexo 提供的命令创建了一个站点。 你可以访问 [Hexo 的文档](https://hexo.io/zh-cn/docs/) 了解如何安装 Hexo 在 Hexo 中有两份主要的配置文件，其名称都是 *_config.yml* 。 其中，一份位于站点根目录下，主要包含 Hexo 本身的配置；另一份位于主题目录下，这份配置由主题作者提供，主要用于配置主题相关的选项。 为了描述方便，在以下说明中，将前者称为站点配置文件， 后者称为主题配置文件。
</blockquote>

<!--more-->
## 安装next

### 下载主题

如果你熟悉 Git， 建议你使用 克隆最新版本 的方式，之后的更新可以通过<font color='red'> git pull </font>来快速更新， 而不用再次下载压缩包替换。

* 克隆最新版本

* 载稳定版本 在终端窗口下，定位到 Hexo 站点目录下。使用 Git checkout 代码：

{%codeblock%}
 cd hexo　　#　进入hexo 文件夹
 git clone https://github.com/iissnan/hexo-theme-next themes/next
{%endcodeblock%}

### 启用主题
与所有 Hexo 主题启用的模式一样。 当 克隆/下载 完成后，打开 站点配置文件， 找到 <font color='red'> theme </font> 字段，并将其值更改为<font color='red'> next </font>  。 启用 NexT 主题
{%codeblock%}
theme: next
{%endcodeblock%}
到此，NexT 主题安装完成。下一步我们将验证主题是否正确启用。在切换主题之后、验证之前， 我们最好使用<font color='red'> hexo clean </font> 来清除 Hexo 的缓存。 
注意 ：这里以后的配置都需要在前面加上空格

## 验证主题
{%codeblock%}
hexo g
hexo s
{%endcodeblock%}
之后用浏览器访问：<font color='red'> https://localhost:4000 </font>如果显示下图所示就说明你已成功安装ＮＥＸＴ主题了