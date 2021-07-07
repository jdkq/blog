---
title: CentOS7系统操作httpd服务
categories: 操作系统
tags: Centos7 Apatch httpd服务
top_img: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586259657396&di=6ececd06fcf372feebabba9f76464a0d&imgtype=0&src=http%3A%2F%2Fimg3.imgtn.bdimg.com%2Fit%2Fu%3D94194178%2C3990624886%26fm%3D214%26gp%3D0.jpg
cover: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586259716551&di=cde1cf0e41822a54a31f5011b296817b&imgtype=0&src=http%3A%2F%2Fc.hiphotos.baidu.com%2Fbaike%2Fw%3D268%2Fsign%3D1cec5434bb389b5038ffe754bd35e5f1%2F9358d109b3de9c82fb65b7a56e81800a19d84393.jpg
abbrlink: 61289
date: 2020-03-18 15:57:35
comments:
hide:
toc:
---
<blockquote>
操作部署某个环境的时候使用的是CentOS7版本，然后在需要启动httpd服务的时候惯性的使用<code>service httpd start</code>命令，但是提示有"/bin/systemctl start  httpd.service"问题。看来系统变动之后一些操作命令还是有些变化的。
</blockquote>

<!--more-->
当然，为了兼容性，我们原来习惯使用的service命令在CentOS7中仍然是可以使用的，它会重定向命令到新的systemctl工具命令，这个我们应该有看到的。但是在这篇文章中，既然用到新的CentOS7，那我们就来看看新的systemctl工具操作命令组，算是一个学习记录，以后应该有需要用到。

## 第一：启动、终止、重启
{%codeblock%}
systemctl start httpd.service #启动
systemctl stop httpd.service #停止
systemctl restart httpd.service #重启
{%endcodeblock%}

## 第二：设置开机启动/关闭
{%codeblock%}
systemctl enable httpd.service #开机启动
systemctl disable httpd.service #开机不启动
{%endcodeblock%}

## 第三：检查httpd状态
{%codeblock%}
systemctl status httpd.service
{%endcodeblock%}