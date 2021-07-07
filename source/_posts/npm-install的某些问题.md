---
title: npm install的某些问题
top_img: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1587039429619&di=128a3d07bee574c1819b6699fbd671d4&imgtype=0&src=http%3A%2F%2Fstatic.leiphone.com%2Fuploads%2Fnew%2Fimages%2F20200317%2F5e70a4538fc03.jpg%3FimageView2%2F2%2Fw%2F740
cover: 'http://img0.imgtn.bdimg.com/it/u=4294296114,2542618876&fm=26&gp=0.jpg'
tags: npm下载包
categories: npm
abbrlink: 35421
date: 2020-04-09 01:07:19
comments:
hide:
toc:
---
## npm err安装报错解决办法

```bash
npm ERR! code ETIMEDOUT
npm ERR! errno ETIMEDOUT
npm ERR! network request to https://registry.npmjs.org/hexo-deployer-git failed, reason: connect ETIMEDOUT 211.136.113.1:8080
npm ERR! network This is a problem related to network connectivity.
npm ERR! network In most cases you are behind a proxy or have bad network settings.
npm ERR! network
npm ERR! network If you are behind a proxy, please make sure that the
npm ERR! network 'proxy' config is set properly.  See: 'npm help config'
```
在执行npm install时出现以上错误，尝试了很多种方法，都没有解决，最后使用http://stackoverflow.com/questions/20397883/npm-doesnt-install-any-modules-network-socket-hangs-up 中的方法，成功解决问题。

> 解决办法：

1.先清除以前代理设置
```bash
npm config set proxy null
npm config set https-proxy null
```
2.重新设置
```bash
npm config set registry http://registry.cnpmjs.org/
```

3.npm install


## 问题2 
```bash
npm ERR! Unexpected end of JSON input while parsing near '...exo-fs","version":"0.'

npm ERR! A complete log of this run can be found in:
npm ERR!     C:\Users\董\AppData\Roaming\npm-cache\_logs\2020-05-15T14_41_43_153Z-debug.log

```

解决办法：  `npm cache clean --force`