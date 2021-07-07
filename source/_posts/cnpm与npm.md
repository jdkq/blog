---
title: cnpm与npm
categories: npm
tags:
  - npm
  - cnpm
top_img: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1587039429619&di=128a3d07bee574c1819b6699fbd671d4&imgtype=0&src=http%3A%2F%2Fstatic.leiphone.com%2Fuploads%2Fnew%2Fimages%2F20200317%2F5e70a4538fc03.jpg%3FimageView2%2F2%2Fw%2F740
cover: 'http://img0.imgtn.bdimg.com/it/u=4294296114,2542618876&fm=26&gp=0.jpg'
abbrlink: 5813
date: 2020-04-04 19:04:51
comments:
hide:
toc:
---
> 就看npm不爽，下载速度死慢死慢，对不住!我没忍住，要斯文点，抱歉...
> 下面介绍一下npm跟cnpm

<!--more-->

## npm
* 允许用户从npm服务器下载别人编写的第三方包使用
* 允许用户从上述服务器下载并安装别人写的命令行程序到本地并且可以使用
* 允许用户将自己写的包或者命令行上传到上述的服务器供别人使用

## npm 命令

* `npm -v` 来测试是否成功安装
* 查看当前目录已安装插件： `npm list`
* 更新全部插件： `npm update [--save-dev]`
* 使用 npm 更新对应插件：`npm update <name> [-g] [--save-dev]`
* 使用 npm 卸载插件： `npm install <name> [-g] [--save-dev]`

## cnpm

* 淘宝团队做的国内镜像，因为npm的服务器位于国外可能会影响安装。淘宝镜像与官方同步频率目前为 10分钟 一次以保证尽量与官方服务同步
* 安装： 命令提示符执行`npm install cnpm -g --registry=https://registry.npm.taobao.org`<br>
[cnpm](/img/cnpm.png)
* `cnpm  -v` 看看是否安装成功

> 插一句（一本正经的bb）: npm下载真的慢，不是电脑的问题！

## 通过改变地址来使用淘宝镜像
* npm的默认地址是 `https://registry.npmjs.org/`
* 可以使用 `npm config get registry` 来查看npm仓库地址
* 可以用 `npm config set registry https://registry.npm.taobao.org` 来改变默认下载地址，达到可以不安装 `cnpm` 就能采用淘宝镜像的目的，然后使用上面的get命令查看是否成功。

## 另外
* `-g` :全局安装
* `-S` :相当于`npm install module_name --save` 写入`package.json` 的 `devDependencies`，这里面的插件只用于开发环境，不用于生产环境，比如 `babel` 、 `webpack打包` 插件就是开发时的需要，真正程序打包并不需要的一些插件
* `-D`:相当于 `npm install module_name --save-dev`，写入 `package.json` 的`devDependencies` , `devDependencies` 里面的插件只用于开发环境，不用于生产环境。比如一些babel编译功能的插件、webpack打包插件就是开发时候的需要，真正程序打包跑起来并不需要的一些插件。

> 为什么要保存在`package.json` 因为node_module包实在是太大了。用一个配置文件保存，只打包安装对应配置文件的插件，按需导入。
