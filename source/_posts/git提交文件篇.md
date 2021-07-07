---
title: git提交文件篇
categories: git
tags: git
top_img: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586260020818&di=7bcd79a28ead4bc3dfb2ef69687d0137&imgtype=0&src=http%3A%2F%2F5b0988e595225.cdn.sohucs.com%2Fimages%2F20190107%2Fc4d3d049a41b4832bd2401e7f209e569.jpeg
cover: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586260119312&di=9cd677b4d0b5d907e8475a60499e4183&imgtype=0&src=http%3A%2F%2Fimg0.imgtn.bdimg.com%2Fit%2Fu%3D3661523940%2C437676520%26fm%3D214%26gp%3D0.jpg
abbrlink: 4312
date: 2020-03-12 11:17:36
comments:
hide:
toc:
---
<blockquote>
    向服务器提交文件
</blockquote>
* 创建描述文档

```bash
    touch README.md
```
* 添加文件
    ```bash
    git add 文件名
    git add . 一键add
    ```
* 提交文件
    ```bash
    git commit -m “提交文件说明”
    git remote add origin git@xx.xx.xx.xx:repos/xxx/xxx/xxx.git
    ```
* 推送到远程仓库
    * 普通推送：
    ```bash
    git push 
    ```
    * 强行推送：
    ```bash
    git push -u origin master
    ```

> 注意如果这一步报错就说明README.md文件没在本地，需要合并一下

```bash
git pull --rebase origin master
```