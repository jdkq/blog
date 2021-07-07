---
title: Hexo主题插入音乐之aplayer音乐播放器
top_img: 'http://pic1.zhimg.com/v2-cc8e99f5d0e3842eea95869deff876cc_1200x500.jpg'
cover: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586378167309&di=bd604ba372e9fa35e4b24df493057281&imgtype=0&src=http%3A%2F%2Fpic2.zhimg.com%2Fv2-a11d47bc3401edaf671f202cd6365a07_1200x500.jpg
tags: hexo-tag-aplayer
categories: hexo
abbrlink: 15999
date: 2020-04-09 01:46:10
comments:
hide:
toc:
---
> 今天折腾的点是给博客中插入音乐，找到的具体可行的方案有：
* 使用音乐平台提供的插件  `体验感很差`
* 使用[hexo-tag-aplayer](https://github.com/MoePlayer/hexo-tag-aplayer)插件  `体验感很好`


## 用音乐平台提供的插件
拿网易云为例，登录网易云网页端，然后点击`生成外链播放器`就能使用
然后在自己的博客上嵌入插件iframe代码
```html
<iframe 
 frameborder="no" border="0" 
 marginwidth="0" marginheight="0" 
 width=530 height=310 
 src="//music.163.com/outchain/player?type=0&id=2205641361&auto=0&height=430">
</iframe>
```
缺点：有版权问题的无法生成外联

## 使用 hexo-tag-aplayer 插件
[hexo-tag-aplayer](https://github.com/MoePlayer/hexo-tag-aplayer)就是[Aplayer](https://github.com/MoePlayer/APlayer)内嵌博客页面的插件

1.安装：
```bash
npm install --save hexo-tag-aplayer
```
原先`hexo-tag-aplayer`不支持`MetingJS`，使得需要图片url，音乐url等等参数，操作起来都很麻烦，需要去音乐网站扒音乐播放链接或者下载下来存储在七牛云或本地

## MeingJS 支持 (3.0 新功能)
MetingJS 是基于Meting API 的 APlayer 衍生播放器，引入 MetingJS 后，播放器将支持对于 QQ音乐、网易云音乐、虾米、酷狗、百度等平台的音乐播放。

1.如果想使用metingjs，首先在根目录配置文件加入如下代码
```confi
aplayer:
  meting: true
```
2.然后在文章中使用metingjs播放器，例如打开网易云音乐网站找到这首coldplay的《Viva la Vida》，从url中可以得到其id为`3986040`，按下面格式即可使用：
```
{% meting "3986040" "netease" "song" "theme:#555" "mutex:true" "listmaxheight:340px" "preload:auto" %}
```
这里的id可以从分享里获取

或者添加个歌单模板：
```
{% meting "972502079" "netease" "playlist" "theme:#555" "mutex:true" "listmaxheight:340px" "preload:auto" %}
```

## 选项列表
选项 | 默认值 | 描述
:-: | :-: | :-:
id | 必须值 | 歌曲 id / 播放列表 id / 相册 id / 搜索关键字| 
server | 必须值 | 音乐平台: `netease`, `tencent`, `xiami`, `baidu`| 
type | 必须值 | `song`, `playlist`, `album`, `search`, `artist`| 
fixed | `false` | 开启固定模式| 
mini | `false` | 开启迷你模式| 
loop | `all` | 列表循环模式：`all`, `one`,`none`| 
order | `list` | 列表播放模式： `list`, `random`| 
volume | 0.7 | 播放器音量| 
lrctype | 0 | 歌词格式类型| 
listfolded | `false` | 指定音乐播放列表是否折叠| 
storagename | `metingjs` | LocalStorage 中存储播放器设定的键名| 
autoplay | `true` | 自动播放，移动端浏览器暂时不支持此功能| 
mutex | `true` | 该选项开启时，如果同页面有其他 aplayer 播放，该播放器会暂停| 
listmaxheight | `340px` | 播放列表的最大长度| 
preload | `auto` | 音乐文件预载入模式，可选项： `none`, `metadata`, `auto`| 
theme | `#ad7a86` | 播放器风格色彩设置|