---
title: Apple官网
tags: 'HTML,CSS'
description: 模仿iphone官网
top_img: https://s3.ax1x.com/2020/12/13/rejOYV.png
comments: false
cover: >-
  https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3396728487,2070953560&fm=11&gp=0.jpg
abbrlink: 59861
date: 2020-12-13 18:32:35
sticky:
categories:
keywords:
toc:
toc_number:
auto_open:
copyright: false
copyright_author:
copyright_author_href:
copyright_url:
copyright_info:
mathjax:
katex:
aplayer:
highlight_shrink: true
---
# Apple官网响应式布局2020
用纯html+css实现苹果官网响应式布局，并且实现不联动的可点击显示再次点击隐藏的下拉菜单

技术支持：
	1. html+css
	2. 字体库iconfont (inconfont.css)
    3. div盒子模型布局模式

{% note success %}
整体效果图
{% endnote %}

![apple](https://s3.ax1x.com/2020/12/20/ra9Uhj.png)


# 头部内容
```html
<head>
    <meta charset="UTF-8">
    <!-- 设置缩小自适应 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- 标题 -->
    <title>Apple（中国大陆）- 官方网站</title>
    <!-- 页面样式css 【apple.css】 -->
    <link rel="stylesheet" href="./apple.css">
    <!-- 标题图标 -->
    <link rel="icon" href="./favicon.ico">
    <!-- CSS图标库API -->
    <link rel="stylesheet" href="./Apple/左右箭头/iconfont.css">
    <link rel="stylesheet" href="./iconfont/iconfont.css">
</head>
```
# 主体内容(body)

{% note success %}
header
{% endnote %}

    * 广告栏
    * 导航栏

## header

```html
<!-- 
        头部 
-->
<header>
    <!-- 广告栏 -->
    <div class="top-box">
        <div class="top-ct">
            <span>&lt;广告&gt;</span>
        </div>
    </div>
    <!-- 导航栏 -->
    <nav>
        <section class="nav-box">
            <ul>
                <li><a href="#"><img src="./Apple/logo1.svg" alt=""></a></li>
                <li><a href="#"><span>Mac</span></a></li>
                <li><a href="#"><span>iPad</span></a></li>
                <li><a href="#"><span>iPhone</span></a></li>
                <li><a href="#"><span>Watch</span></a></li>
                <li><a href="#"><span>Music</span></a></li>
                <li><a href="#"><span>技术支持</span></a></li>
                <li><a href="#"></a></li>
                <li><a href="#"></a></li>
            </ul>
            <ol>
                <li><a href="#">
                    <a href="#"><i class="iconfont icon-hengxian1"></i></a>
                </li>
                <li>
                    <a href="#"><img src="./Apple/logo1.svg" alt=""></a>
                </li>
                <li><a href="#"></a></li>
            </ol>
        </section>
    </nav>
</header>
```
```css
/*清除默认样式*/
*{
    margin: 0;
    padding: 0;
    text-decoration: none;
    list-style: none;
}
/*设置宽为屏占满自适应*/
body,html{
    width: 100%;
}


/*
    头部
*/
.header{
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 30;
}

/*
    广告栏样式
*/

header .top-box{
    height: 40px;
    background-color: #444;
}
.top-box .top-ct{
    height: 100%;
    width: 976px;
    font-size: 12px;
    color: #a8a8aa;
    margin: 0 auto;
    line-height: 40px;
    text-align: right;
}

/*
        
    导航栏的样式

*/

header nav{
    height: 44px;
    background-color: rgba(0,0,0,0.92);
}
.nav-box{
    width: 976px;
    height: 100%;
    margin: 0 auto;
    overflow: hidden;
}
/*
    选择第八个子代列表添加搜索符号链接
*/
.nav-box ul li:nth-child(8) a{
    display: block;
    width: 18px;
    height: 88px;
    background-size: 18px 88px;
    background-repeat: no-repeat;
    background-image: url(./Apple/logo2.svg);
    background-position: center -44px;
    /* background-color: red; */
}
/*
    选择最后一个子代列表添加 购物车 符号链接
*/
.nav-box ul li:last-child a{
    display: block;
    width: 17px;
    height: 44px;
    background-size: 17px 44px;
    background-repeat: no-repeat;
    background-image: url(./Apple/logo3.svg);
    background-position: center center;
    /* background-color: red; */
}
.nav-box ul{
    /*
        样式改为固定flex格式（不会随鼠标滑轮滚动而消失）
    */
    display: flex;
    height: 44px;
    justify-content: space-between;
    align-items: flex-start;
    line-height: 44px;
}
.nav-box ul li a span{
    font-size: 14px;
    color: #c2c2c7;
}
```

## Header布局效果图

![header](https://s3.ax1x.com/2020/12/13/rezDQU.png)

{% note success %}
main (内容栏)
{% endnote %}

    * iphone12
    * iphone12mini
    * watch
    * imgbox iPhone宣传产品图片

## main

```html    
<!-- 内容栏 -->
<main>
    <!-- iphone12栏 -->

    <div class="iphone12">
        <div class="zaixian">
            <p>
                <a href="#">在线选购</a>
                <span>
                    ,享受免费送货、Specialist专家支持、免息分期等服务。
                </span>
            </p>
        </div>
        <div class="phone12-top">
            <h1>iPhone 12 Pro</h1>
            <h2>自我再飞跃。</h2>
            <div class="phtp-a">
                <a href="#">进一步了解<i class="iconfont icon-arrow-backimg"></i></a>
                <a href="#">立刻抢购<i class="iconfont icon-arrow-backimg"></i></a>
            </div>
        </div>
        <div class="phone12-bom">
            <span>iPhone 12 Pro Max</span>
        </div>
    </div>

    <!-- iphone12mini页 -->
    <div class="iphone12mini">
        <div class="phone12-top">
            <h1>iPhone 12</h1>
            <h2>升维大提速。</h2>
            <div class="phtp-a">
                <a href="#">进一步了解<i class="iconfont icon-arrow-backimg"></i></a>
                <a href="#">立刻抢购<i class="iconfont icon-arrow-backimg"></i></a>
            </div>
        </div>
        <div class="phone12-bom">
            <span>iPhone 12 mini</span>
        </div>
    </div>

    <!-- apple watch手表页 -->

    <div class="watch">
        <div class="phone12-top">
            <img src="./Apple/white-watc  .png" alt="">
            <h2>健康的未来，现在间戴上。</h2>
            <div class="phtp-a">
                <a href="#">进一步了解<i class="iconfont icon-arrow-backimg"></i></a>
                <a href="#">选购<i class="iconfont icon-arrow-backimg"></i></a>
            </div>
        </div>
    </div>

    <!-- imgbox iPhone宣传产品图片 -->

    <div class="imgbox">
       <div>
            <h1>iPad Air</h1>
            <p>凭实力出彩。</p>
            <a href="#">进一步了解<i class="iconfont icon-arrow-backimg"></i></a>
            <a href="#">购买<i class="iconfont icon-arrow-backimg"></i></a>
       </div>
       <div>
            <h1>HomePod mini</h1>
            <a href="#">进一步了解<i class="iconfont icon-arrow-backimg"></i></a>
            <a href="#">查看价格<i class="iconfont icon-arrow-backimg"></i></a>
       </div>
       <div>
            <h1>App Store</h1>
            <p>无数可心 App,一个可靠来源。</p>
            <a href="#">进一步了解<i class="iconfont icon-arrow-backimg"></i></a>
       </div>
       <div>
            <img src="./Apple/logo-tile__ec23lf7d072a_large.png" alt="">
            <p>特有本事,特超值。</p>
            <a href="#">进一步了解<i class="iconfont icon-arrow-backimg"></i></a>
            <a href="#">购买<i class="iconfont icon-arrow-backimg"></i></a>
       </div>
       <div>
            <img src="./Apple/black-watc  .png" alt="">
            <p>事事拿手,轻松入手。</p>
            <a href="#">进一步了解<i class="iconfont icon-arrow-backimg"></i></a>
            <a href="#">购买<i class="iconfont icon-arrow-backimg"></i></a>
       </div>
       <div>
           <img src="./Apple/music.png" alt="">
           <p>KatyPerry全新专辑《Smile》上线,<br>听起来，笑起来。</p>
           <p>
                <a href="#">免费试用<sup>1</sup><i class="iconfont icon-arrow-backimg"></i></a>
                <a href="#">进一步了解<i class="iconfont icon-arrow-backimg"></i></a>
           </p>
           <img src="./Apple/music-ogo.png" alt="">
       </div>
    </div>
</main>
```
```css
/*
    main内容
*/

/*
    
    内容栏

*/
main{
    margin-top: 88px;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    padding-bottom: 15px;
}
main .zaixian{
    height: 44px;
    background-color: #fff;
    line-height: 44px;
    text-align: center;
}
.zaixian a{
    font-size: 13px;
    color: #0066cc;
}
.zaixian span{
    font-size: 13px;
    color: #1d1d1f;
}
/*

    iphone12栏样式

*/
main .iphone12{
    /* background-color: #000; */
    width: 100%;
    height: 786px;
    background-image: url(./Apple/max/max-one.jpg);
    background-repeat: no-repeat;
    background-position: center center;
    position: relative;
}
.iphone12 .phone12-top{
    margin-top: 35px;
    text-align: center;
}
.iphone12 .phone12-top h1{
    font-size: 56px;
    font-weight: 600;
    color: #f5f5f7;
}
.iphone12 .phone12-top h2{
    font-size: 28px;
    font-weight: 400;
    color: #f5f5f7;
    margin-top: -5px;
}
.iphone12 .phone12-top .phtp-a{
    margin-top: 15px;
}
.iphone12 .phone12-top .phtp-a a:last-child{
    margin-left: 35px;
}
.iphone12 .phone12-top .phtp-a a{
    color: #2997ff;
    font-size: 20px;
}
.iphone12 .phone12-top .phtp-a a i{
    color: #2997ff;
    font-size: 20px;
}
.iphone12 .phone12-bom{
    text-align: center;
    position: absolute;
    left: 0;
    right: 0;
    margin: 0 auto;
    bottom: 51px;
}
.iphone12 .phone12-bom span{
    font-size: 21px;
    color: #f5f5f7;
}
.iphone12 .phone12-bom p{
    font-size: 21px;
    color: #a1a1a6;
}
/*
    设置最后一个子p偏移量为20px
*/
.iphone12 .phone12-bom p:last-child{
    margin-top: 20px;
}

/*

    iphone12mini页

*/

.iphone12mini{
    width: 100%;
    height: 903px;
    background-image: url(./Apple/max/max-two.jpg);
    background-repeat: no-repeat;
    background-position: center center;
    position: relative;
}
.iphone12mini .phone12-top{
    margin-top: 35px;
    text-align: center;
}
.iphone12mini .phone12-top h1{
    font-size: 56px;
    font-weight: 600;
    color: #000;
}
.iphone12mini .phone12-top h2{
    font-size: 28px;
    font-weight: 400;
    color: #000;
    margin-top: -5px;
}
.iphone12mini .phone12-top .phtp-a{
    margin-top: 15px;
}
.iphone12mini .phone12-top .phtp-a a:last-child{
    margin-left: 35px;
}
.iphone12mini .phone12-top .phtp-a a{
    color: #2997ff;
    font-size: 20px;
}
.iphone12mini .phone12-top .phtp-a a i{
    color: #2997ff;
    font-size: 20px;
}
.iphone12mini .phone12-bom{
    text-align: center;
    position: absolute;
    left: 0;
    right: 0;
    margin: 0 auto;
    bottom: 65px;
}
.iphone12mini .phone12-bom span{
    font-size: 21px;
    color: #000;
}
.iphone12mini .phone12-bom p{
    font-size: 21px;
    color: #a1a1a6;
}
.iphone12mini .phone12-bom p:last-child{
    margin-top: 20px;
}


/*

    apple watch手表页

*/


main .watch{
    /* background-color: #000; */
    width: 100%;
    height: 694px;
    background-image: url(./Apple/max/max-three.jpg);
    background-repeat: no-repeat;
    background-position: center 200px;
    position: relative;
    background-color: #000;
}
.watch .phone12-top{
    margin-top: 35px;
    text-align: center;
}
.watch .phone12-top h2{
    font-size: 22px;
    font-weight: 400;
    color: #f5f5f7;
    margin-top: 5px;
}
.watch .phone12-top .phtp-a{
    margin-top: 15px;
}
.watch .phone12-top .phtp-a a:last-child{
    margin-left: 35px;
}
.watch .phone12-top .phtp-a a{
    color: #2997ff;
    font-size: 20px;
}
.watch .phone12-top .phtp-a a i{
    color: #2997ff;
    font-size: 20px;
}

/*

    imgbox iPhone宣传产品图片

*/


main .imgbox{
    /*设置图片为弹性布局格式*/
    display: flex;
    /*
        让弹性div盒子进行拆行
    */
    flex-wrap: wrap;
    /*
        在弹性盒对象的 <div> 元素中的各项周围留有空白
    */
    justify-content: space-around;
    /*
        项目在主轴上的对齐方式为左侧
    */
    align-items: flex-start;
    padding: 0 5px;
}
main .imgbox div{
    /*
        设置div盒子自适应函数
    */
    width: calc((100% - 5px * 4) / 2);
    height: 624px;
    background-color: #FBFBFD;
    margin-top: 10px;
    cursor: pointer;
}
.imgbox>div:first-child{
    background-image: url(./Apple/max/unit-max1.jpg);
    background-repeat: no-repeat;
    background-position: center center;
    text-align: center;
}
.imgbox>div:first-child h1{
    margin-top: 45px;
    font-size: 40px;
}
.imgbox>div:first-child p{
    margin-bottom: 10px;
    font-size: 20px;
}
.imgbox>div:first-child a{
    color: #2997ff;
    margin-right: 20px;
}
.imgbox>div:first-child a i{
    color: #2997ff;
}
.imgbox>div:nth-child(2){
    background-image: url(./Apple/max/unit-max2.jpg);
    background-repeat: no-repeat;
    background-position: center center;
    text-align: center;
}
.imgbox>div:nth-child(2) h1{
    font-size: 40px;
    margin-top: 470px;
}
.imgbox>div:nth-child(2) a{
    color: #2997ff;
    margin-right: 20px;
}
.imgbox>div:nth-child(2) a i{
    color: #2997ff;
}
.imgbox>div:nth-child(3){
    background-image: url(./Apple/max/unit-max3.jpg);
    background-repeat: no-repeat;
    background-position: center center;
    text-align: center;
}
.imgbox>div:nth-child(3) h1{
    margin-top: 45px;
    font-size: 40px;
}
.imgbox>div:nth-child(3) p{
    margin-bottom: 10px;
    font-size: 20px;
}
.imgbox>div:nth-child(3) a{
    color: #2997ff;
    margin-right: 20px;
}
.imgbox>div:nth-child(3) a i{
    color: #2997ff;
}
.imgbox>div:nth-child(4){
    background-image: url(./Apple/max/unit-max4.jpg);
    background-repeat: no-repeat;
    background-position: center center;
    text-align: center;
}
.imgbox>div:nth-child(4) img{
    margin-top: 390px;
}
.imgbox>div:nth-child(4) p{
    margin-bottom: 10px;
    font-size: 18px;
}
.imgbox>div:nth-child(4) a{
    color: #2997ff;
    margin-right: 20px;
}
.imgbox>div:nth-child(4) a i{
    color: #2997ff;
}
.imgbox>div:nth-child(5){
    background-image: url(./Apple/max/unit-max5.jpg);
    background-repeat: no-repeat;
    background-position: center 200px;
    text-align: center;
}
.imgbox>div:nth-child(5) img{
    margin-top: 35px;
    margin-bottom: 10px;
}
.imgbox>div:nth-child(5) p{
    margin-bottom: 10px;
    font-size: 20px;
}
.imgbox>div:nth-child(5) a{
    color: #2997ff;
    margin-right: 20px;
}
.imgbox>div:nth-child(5) a i{
    color: #2997ff;
}
.imgbox>div:nth-child(6){
    background-image: url(./Apple/max/unit-max6.jpg);
    background-repeat: no-repeat;
    background-position: center center;
    background-size: auto 624px;
    text-align: center;
}
.imgbox>div:nth-child(6) img:first-child{
    margin-top: 370px;
    margin-bottom: 10px;
}
.imgbox>div:nth-child(6) p:nth-child(2){
    margin-bottom: 10px;
    font-size: 18px;
    color: #f5f5f7;
}
.imgbox>div:nth-child(6) a{
    color: #f5f5f7;
    margin-right: 20px;
    font-weight: 200;
}
.imgbox>div:nth-child(6) a i{
    color: #f5f5f7;
    font-weight: 200;
}
.imgbox>div:nth-child(6) img:last-child{
    margin-top: 28px;
}

/*
    
    设置伪类效果

*/

main .iphone12,
.iphone12mini,
.watch{
    /*
        移入变成小手
    */
    cursor: pointer;
}
main .iphone12 .zaixian{
    /*
        移入变默认
    */
    cursor: initial;
}
main a:hover{
    /*
        移入变下边线
    */
    text-decoration: underline;
}
.nav-box ul li a span:hover{
    /*
        移入改变字体大小及颜色
    */
    font-size: 14px;
    color: #fff;
}
/*
    移入更改图片
*/
.nav-box ul li:nth-child(8) a:hover{
    display: block;
    width: 18px;
    height: 88px;
    background-size: 18px 88px;
    background-repeat: no-repeat;
    background-image: url(./Apple/logo2.svg);
    background-position: center center;
    /* background-color: red; */
}

```


## main布局效果图

![main](https://s3.ax1x.com/2020/12/13/rezoOe.png)

{% note success %}
footer底栏
{% endnote %}

    * footer底部利用<dl> 标签定义了定义列表<dl> 标签用于结合 <dt> （定义列表中的项目）和 <dd> （描述列表中的项目）。

## Footer

```html
    <!-- 尾部footer -->
    <footer>
        <section class="footer-box">
            <div class="dingyue">
                <span>1. 免费试用期结束后，每月收费 RMB 10。无需合约。当试用期结束后，会员方案将按月自动续订，直至取消订阅。</span>
            </div>
            <section class="dl-box">
                <dl>
                    <dt>选购及了解</dt>
                    <a href="#">
                        <dd>Mac</dd>
                    </a>
                    <a href="#">
                        <dd>iPad</dd>
                    </a>
                    <a href="#">
                        <dd>iPhone</dd>
                    </a>
                    <a href="#">
                        <dd>Watch</dd>
                    </a>
                    <a href="#">
                        <dd>Music</dd>
                    </a>
                    <a href="#">
                        <dd>AirPods</dd>
                    </a>
                    <a href="#">
                        <dd>HomePod</dd>
                    </a>
                    <a href="#">
                        <dd>iPod touch</dd>
                    </a>
                    <a href="#">
                        <dd>配件</dd>
                    </a>
                    <a href="#">
                        <dd>App Store 充值卡</dd>
                    </a>
                </dl>
                <div class="dl-one">
                    <dl>
                        <dt>服务</dt>
                        <a href="#">
                            <dd>Apple Music</dd>
                        </a>
                        <a href="#">
                            <dd>iCloud</dd>
                        </a>
                        <a href="#">
                            <dd>Apple Pay</dd>
                        </a>
                    </dl>
                    <dl>
                        <dt>账户</dt>
                        <a href="#">
                            <dd>管理你的 Apple ID</dd>
                        </a>
                        <a href="#">
                            <dd>Apple Store 账户</dd>
                        </a>
                        <a href="#">
                            <dd>iCloud.com</dd>
                        </a>
                    </dl>
                </div>
                <dl>
                    <dt>Apple Store 商店</dt>
                    <a href="#">
                        <dd>查找零售店</dd>
                    </a>
                    <a href="#">
                        <dd>在线选购</dd>
                    </a>
                    <a href="#">
                        <dd>Genius Bar 天才吧</dd>
                    </a>
                    <a href="#">
                        <dd>Today at Apple</dd>
                    </a>
                    <a href="#">
                        <dd>Apple 夏令营</dd>
                    </a>
                    <a href="#">
                        <dd>Apple Store App</dd>
                    </a>
                    <a href="#">
                        <dd>翻新和优惠</dd>
                    </a>
                    <a href="#">
                        <dd>分期付款</dd>
                    </a>
                    <a href="#">
                        <dd>Apple Trade In 换购计划</dd>
                    </a>
                    <a href="#">
                        <dd>订单状态</dd>
                    </a>
                    <a href="#">
                        <dd>选购帮助</dd>
                    </a>
                </dl>
                <div class="dl-two">
                    <dl>
                        <dt>商务应用</dt>
                        <a href="#">
                            <dd>Apple 与商务</dd>
                        </a>
                        <a href="#">
                            <dd>商务选购</dd>
                        </a>
                    </dl>
                    <dl>
                        <dt>教育应用</dt>
                        <a href="#">
                            <dd>Apple 与教育</dd>
                        </a>
                        <a href="#">
                            <dd>高校师生选购</dd>
                        </a>
                    </dl>
                </div>
                <div class="dl-three">
                    <dl>
                        <dt>Apple 价值观</dt>
                        <a href="#">
                            <dd>辅助功能</dd>
                        </a>
                        <a href="#">
                            <dd>环境责任</dd>
                        </a>
                        <a href="#">
                            <dd>隐私</dd>
                        </a>
                        <a href="#">
                            <dd>供应商责任</dd>
                        </a>
                    </dl>
                    <dl>
                        <dt>关于 Apple</dt>
                        <a href="#">
                            <dd>Newsroom</dd>
                        </a>
                        <a href="#">
                            <dd>Apple 管理层</dd>
                        </a>
                        <a href="#">
                            <dd>工作机会</dd>
                        </a>
                        <a href="#">
                            <dd>创造就业</dd>
                        </a>
                        <a href="#">
                            <dd>活动</dd>
                        </a>
                        <a href="#">
                            <dd>联系 Apple</dd>
                        </a>
                    </dl>
                </div>
            </section>
            <p>更多选购方式：<a href="#">查找你附近的 Apple Store 零售店</a>及，<a href="#">更多门店</a>或者致电 400-666-8800。</p>
            <span>Copyright © 2020 Apple Inc. 保留所有权利。</span>
            <a href="#">隐私政策</a><span>｜</span>
            <a href="#">使用条款</a><span>｜</span>
            <a href="#">销售政策</a><span>｜</span>
            <a href="#">法律信息</a><span>｜</span>
            <a href="#">网站地图</a>
            <h3>京ICP备10214630 营业执照 无线电发射设备销售备案编号11201910351200</h3>
        </section>
        <section class="footer-mini">
            <p>
                1. 免费试用期结束后，每月收费 RMB 10。无需合约。当试用期结束后，会员方案将按月自动续订，直至取消订阅。
            </p>
            <input type="checkbox" id="input-1">
            <input type="checkbox" id="input-2">
            <input type="checkbox" id="input-3">
            <input type="checkbox" id="input-4">
            <input type="checkbox" id="input-5">
            <input type="checkbox" id="input-6">
            <input type="checkbox" id="input-7">
            <input type="checkbox" id="input-8">
            <label for="input-1" class="label-one">
                <div>
                    <span>选购及了解</span>
                    <b></b>
                </div>
                <dl>
                    <a href="#">
                        <dd>Mac</dd>
                    </a>
                    <a href="#">
                        <dd>iPad</dd>
                    </a>
                    <a href="#">
                        <dd>iPhone</dd>
                    </a>
                    <a href="#">
                        <dd>Watch</dd>
                    </a>
                    <a href="#">
                        <dd>Music</dd>
                    </a>
                    <a href="#">
                        <dd>AirPods</dd>
                    </a>
                    <a href="#">
                        <dd>HomePod</dd>
                    </a>
                    <a href="#">
                        <dd>iPod touch</dd>
                    </a>
                    <a href="#">
                        <dd>配件</dd>
                    </a>
                    <a href="#">
                        <dd>App Store 充值卡</dd>
                    </a>
                </dl>
            </label>
            <label for="input-2" class="label-two">
                <div>
                    <span>服务</span>
                    <b></b>
                </div>
                <dl>
                    <a href="#">
                        <dd>Apple Music</dd>
                    </a>
                    <a href="#">
                        <dd>iCloud</dd>
                    </a>
                    <a href="#">
                        <dd>Apple Pay</dd>
                    </a>
                </dl>
            </label>
            <label for="input-3" class="label-three">
                <div>
                    <span>账户</span>
                    <b></b>
                </div>
                <dl>
                    <a href="#">
                        <dd>管理你的 Apple ID</dd>
                    </a>
                    <a href="#">
                        <dd>Apple Store 账户</dd>
                    </a>
                    <a href="#">
                        <dd>iCloud.com</dd>
                    </a>
                </dl>
            </label>
            <label for="input-4" class="label-four">
                <div>
                    <span>Apple Store 商店</span>
                    <b></b>
                </div>
                <dl>
                    <a href="#">
                        <dd>查找零售店</dd>
                    </a>
                    <a href="#">
                        <dd>在线选购</dd>
                    </a>
                    <a href="#">
                        <dd>Genius Bar 天才吧</dd>
                    </a>
                    <a href="#">
                        <dd>Today at Apple</dd>
                    </a>
                    <a href="#">
                        <dd>Apple 夏令营</dd>
                    </a>
                    <a href="#">
                        <dd>Apple Store App</dd>
                    </a>
                    <a href="#">
                        <dd>翻新和优惠</dd>
                    </a>
                    <a href="#">
                        <dd>分期付款</dd>
                    </a>
                    <a href="#">
                        <dd>Apple Trade In 换购计划</dd>
                    </a>
                    <a href="#">
                        <dd>订单状态</dd>
                    </a>
                    <a href="#">
                        <dd>选购帮助</dd>
                    </a>
                </dl>
            </label>
            <label for="input-5" class="label-five">
                <div>
                    <span>商务应用</span>
                    <b></b>
                </div>
                <dl>
                    <a href="#">
                        <dd>Apple 与商务</dd>
                    </a>
                    <a href="#">
                        <dd>商务选购</dd>
                    </a>
                </dl>
            </label>
            <label for="input-6" class="label-six">
                <div>
                    <span>教育应用</span>
                    <b></b>
                </div>
                <dl>
                    <a href="#">
                        <dd>Apple 与教育</dd>
                    </a>
                    <a href="#">
                        <dd>高校师生选购</dd>
                    </a>
                </dl>
            </label>
            <label for="input-7" class="label-seven">
                <div>
                    <span>Apple 价值观</span>
                    <b></b>
                </div>
                <dl>
                    <a href="#">
                        <dd>辅助功能</dd>
                    </a>
                    <a href="#">
                        <dd>环境责任</dd>
                    </a>
                    <a href="#">
                        <dd>隐私</dd>
                    </a>
                    <a href="#">
                        <dd>供应商责任</dd>
                    </a>
                </dl>
            </label>
            <label for="input-8" class="label-eight">
                <div>
                    <span>关于 Apple</span>
                    <b></b>
                </div>
                <dl>
                    <a href="#">
                        <dd>Newsroom</dd>
                    </a>
                    <a href="#">
                        <dd>Apple 管理层</dd>
                    </a>
                    <a href="#">
                        <dd>工作机会</dd>
                    </a>
                    <a href="#">
                        <dd>创造就业</dd>
                    </a>
                    <a href="#">
                        <dd>活动</dd>
                    </a>
                    <a href="#">
                        <dd>联系 Apple</dd>
                    </a>
                </dl>
            </label>
            <h3>
                更多选购方式：<a href="#">查找你附近的 Apple Store 零售店</a>及<a href="#">更多门店</a>，或者致电 400-666-8800。
            </h3>
            <h3>
                Copyright © 2020 Apple Inc. 保留所有权利。
            </h3>
            <p>
                <a href="#"><span>隐私政策</span></a><span>｜</span>
                <a href="#"><span>使用条款</span></a><span>｜</span>
                <a href="#"><span>销售政策</span></a><span>｜</span>
                <a href="#"><span>法律信息</span></a><span>｜</span>
                <a href="#"><span>网站地图</span></a>
            </p>
            <p>
                <a href="#"><span>京ICP备10214630</span></a><a href="#"> 营业执照 </a><span>无线电发射设备销售备案编号11201910351200</span>
            </p>
        </section>
    </footer>
```
```css
/*

    footer底部
    利用<dl> 标签定义了定义列表
    <dl> 标签用于结合 <dt> （定义列表中的项目）和 <dd> （描述列表中的项目）。

*/

footer{
    height: 515px;
    background-color: #f5f5f7;
    padding-bottom: 20px;
}
footer .footer-box{
    width: 976px;
    height: 100%;
    /* background-color: #fff; */
    margin: 0 auto;
}
.footer-box .dingyue{
    font-size: 12px;
    color: #ccc;
    padding: 17px 0 20px 0;
    border-bottom: 1px solid #ccc;
}
.footer-box dt{
    font-size: 12px;
    font-weight: bold;
    color: #1d1d1f;
}
.footer-box dd{
    font-size: 12px;
    color: #999;
    margin-top: 10px;
}
.footer-box .dl-box{
    display: flex;
    margin-top: 25px;
    justify-content: space-between;
    padding-right: 125px;
}
.dl-box div>dl:last-child{
    margin-top: 30px;
}
.footer-box p{
    font-size: 12px;
    color: #ccc;
    padding: 30px 0 10px 0;
    border-bottom: 1px solid #ccc;
}
.footer-box a{
    font-size: 12px;
    color: #2997ff;
}
.footer-box p a:hover{
    text-decoration: underline;
    color: #2997ff;
}
.footer-box>span{
    font-size: 12px;
    color: #ccc;
}
.footer-box>a{
    font-size: 12px;
    color: #999;
}
.footer-box>a:nth-child(5){
    padding-left: 25px;
}
.footer-box h3{
    margin-top: 5px;
    font-weight: 400;
    font-size: 12px;
    color: #999;
}
.footer-box a:hover{
    text-decoration: underline;
    color: #333;
}
.footer-box dd:hover{
    color: #333;
}
footer .footer-mini{
    display: none;
}
footer .footer-mini input{
    display: none;
}

```


## footer布局效果图

![footer](https://s3.ax1x.com/2020/12/13/reztds.png)

# 整体效果展示
[点击这里](https://asdsa.top/apple/)