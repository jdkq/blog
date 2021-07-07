---
title: npm安装、更新与卸载
tags: npm介绍
categories: npm
top_img: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1587039429619&di=128a3d07bee574c1819b6699fbd671d4&imgtype=0&src=http%3A%2F%2Fstatic.leiphone.com%2Fuploads%2Fnew%2Fimages%2F20200317%2F5e70a4538fc03.jpg%3FimageView2%2F2%2Fw%2F740
cover: 'http://img0.imgtn.bdimg.com/it/u=4294296114,2542618876&fm=26&gp=0.jpg'
abbrlink: 63389
date: 2020-03-16 14:48:01
comments:
hide:
toc:
---
<blockquote>
	npm 为你和你的团队打开了连接整个 JavaScript 天才世界的一扇大门。它是世界上最大的软件注册表，每星期大约有 30 亿次的下载量，包含超过 600000 个 包（package） （即，代码模块）。来自各大洲的开源软件开发者使用 npm 互相分享和借鉴。包的结构使您能够轻松跟踪依赖项和版本。
</blockquote>

<!--more-->
## npm 由三个独立的部分组成：
* 网站
	* 是开发者查找包（package）、设置参数以及管理 npm 使用体验的主要途径。
* 注册表（registry）
	* 是一个巨大的数据库，保存了每个包（package）的信息。
* 命令行工具
	* 通过命令行或终端运行。开发者通过 CLI 与 npm 打交道


## 安装途径：
从　node.js 官网进行安装


## 安装过程
> window10系统

**百度搜索nodejs**
进入官网选择windows进行下载

>
> linux -就拿deepinOS来说
>
> 这里有三种方法

### 1. 官方途径：通过包管理器方式安装

* node8版本：

```bash
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

* node10版本：

```bash
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
```
参考官方教程,但是很奇怪，会报错，猜测deepin系统的原因。

### 2.通过源码编译安装

在node官网下载专区找到系统对应的版本，鼠标右键复制链接。打开deepin终端输入：

1. 下载node

```bash
wget https://nodejs.org/dist/v8.11.4/node-v8.11.4-linux-x64.tar.xz
```

2. 解压文件

```bash
tar -xvf node-v8.11.4-linux-x64.tar.xz
```
3. 切换并查看node所在路径

```bash
cd node-v8.11.4-linux-x64/bin
pwd

```

4. 查看node版本

```bash
node -v
```
5. 将node和npm设置为全局 （注意路径为上述第3部的路径）

```bash
sudo ln /home/ubuntu/node-v8.11.4-linux-x64/bin/node /usr/local/bin/node
sudo ln /home/ubuntu/node-v8.11.4-linux-x64/bin/npm /usr/local/bin/npm
pwd
```

这种方法配置的环境容易出问题，在安装http-server时依然报错。

### 3.使用自带的apt安装

* 安装node与npm
```bash
sudo apt install nodejs
sudo apt install npm
```
* 安装管理nodejs 本身工具，n模块
```bash
sudo npm install -g n
```
* 升级 node 到制定版本，后接版本号
```bash
sudo n latest //最新版本
sudo n stable //稳定版本
sudo n lts //长期支持版本
```
* 升级 npm 到最新版本
```bash
sudo npm install npm@latest -g
```

## 利用npm下载本地包

```bash
#下载
npm install <package_name> #自动创建一个node_modules目录
npm -v

#更新
cd <需要更新的路径根目录>
npm update <package_name>
    
#卸载
cd <需要卸载的路径根目录>
npm uninstall <package_name>
```

## 利用npm下载全局包
```bash
#下载
npm install -g <package_name>
#更新
npm update -g <package_name>
#卸载
npm uninstall -g <package_name>
```
## “全局包”跟“本地包”的区别：

* 全局包：下载到电脑本地，可应用于所有
* 本地包：只作用于本地根目录
