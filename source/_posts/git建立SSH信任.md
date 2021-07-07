---
title: git建立SSH信任
categories: git
tags: ssh root@×××××
top_img: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586259952574&di=746442ef76fd96207ac0fe1214c99ad8&imgtype=0&src=http%3A%2F%2Fsshno2018.fi%2Fwp-content%2Fuploads%2F2017%2F12%2FSSHNO_logo12_2017.jpg
cover: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586259829646&di=fd4727dd93a6db00af11fc2b5226ee83&imgtype=0&src=http%3A%2F%2Fimg3.imgtn.bdimg.com%2Fit%2Fu%3D1366982948%2C650556575%26fm%3D214%26gp%3D0.jpg
abbrlink: 31838
date: 2020-03-23 18:46:42
comments:
hide:
toc:
---
## 准备:
* 在本地生成公钥和密钥： <code>ssh-keygen -t rsa</code>
* 将本地生成的公钥发送到服务器上（建立信任关系）：<br>
{%codeblock%}
#注意这里UserName、root、server_ip 一定要看好
ssh-copy-id -i C:/Users/UserName/.ssh/id_rsa.pub root@server_ip
{%endcodeblock%}
* 测试ssh远程登陆是否成功：<code>ssh root@server_ip</code>

## 出现的错误error解析
> git添加公钥后报错`sign_and_send_pubkey: signing failed: agent refused operation`的解决办法：

```bash
ssh-agent -s
ssh-add
```
<!--more-->

## 附带：
git_bash下载链接：
https://pan.baidu.com/s/1Cte-CWLJtYwReabmUxBeRw
提取码：rila