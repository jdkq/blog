---
title: 深度deepinos20 beta
tags: DeepinOs
categories: 操作系统
top_img: 'https://www.deepin.org/wp-content/uploads/2020/04/zh.jpg'
cover: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1587134092332&di=c9a6f38a78f2d1e3f95c1f6f083295ca&imgtype=0&src=http%3A%2F%2Fimg0.imgtn.bdimg.com%2Fit%2Fu%3D1681015405%2C3511786507%26fm%3D214%26gp%3D0.jpg
abbrlink: 11524
date: 2020-04-17 18:45:01
comments:
top:
---
![deepin20beta展图](https://www.deepin.org/wp-content/uploads/2020/04/zh.jpg)
深度操作系统是一个致力于为全球用户提供美观易用、安全可靠的Linux发行版。

深度操作系统 20 Beta采取统一的设计风格，从桌面环境和应用重新进行设计，其中底层仓库、内核分别升级到Debian 10、Kernel 5.3，全新的设计带来不一样的交互体验，同时不断优化系统各个方面，带来更加丰富的应用生态和系统稳定性，本次深度应用家族也带来全新的设计和新的应用。

## 新版效果图

**令您耳目一新的deepin桌面环境**

焕然一新的图形界面，具备独树一帜的圆角窗口设计，自然、平滑的动画过渡效果，精美绝伦的多任务视图，别出心裁的配色与图标设计，处处精心，只为令您心动的操作体验。

![deepinos20beta destop](https://www.deepin.org/wp-content/uploads/2020/04/01-1.jpg)

**支持更多硬件的新版稳定内核**

新版自带内核升级到最新Kernel 5.3版本，系统稳定性和兼容性方面得到了大大的提升，支持更多的硬件设备。

![kernel5.3](https://www.deepin.org/wp-content/uploads/2020/04/03.jpg)


> 我感觉较于`deepinos15.11`版本相比，更类似于`统一操作系统v20`

## 双系统安装

> 官方镜像下载链接：http://cdimage.deepin.com/releases/20Beta/

![download](https://ae01.alicdn.com/kf/Hfccb571e1db84b43a577cbd655eddcf9f.png)


## 步骤参考

> 链接：https://blog.csdn.net/qq_35379989/article/details/83515882


## 补充
**如果你是deepinos15.11的系统版本 想在不重装的前提下升级到新版20beta就看下面步骤**

* 打开deepin终端

* `sudo dedit /etc/apt/sources.list` 然后复制保存下列代码
```
deb [by-hash=force] http://community-packages.deepin.com/deepin/ apricot main contrib non-free
#deb-src http://community-packages.deepin.com/deepin/ apricot main contrib non-free
```
* 更新系统源 `sudo apt update` + `sudo apt full-upgrade`

> 这一步死长死长，一定要在网络通畅的地方执行上述代码

* 处理激活问题 `sudo apt remove deepin-aiassistant`

* 重启电脑

*成功截图：*
![重启后开机等待一会显示内容](https://ae01.alicdn.com/kf/H73e33e565a604260901dbde444e531acu.jpg)

![deepinos20beta界面](https://ae01.alicdn.com/kf/Hda36795960a04f548abf8fe4a1cdff19O.png)


## 体验

> 看评论吧，我还在下载中 ...
