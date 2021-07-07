---
title: MVC跟MVVM
tags:
  - vue
  - MVC
  - MVVM
categories: Web前端
top_img: http://p0.qhimg.com/bdr/__85/t0133ce3da099a5773a.jpg
cover: https://5b0988e595225.cdn.sohucs.com/images/20180621/55a7c22bc6ae4debb81c34367837460d.jpeg
comments: false
top: true
abbrlink: 54511
date: 2020-04-24 12:21:18
---

## Node (后端) 中的MVC 与前端中的MVVM 之间的区别跟概念
M(model处理数据的crud) V(view) C(业务逻辑处理层 登录&& 注销)
`MVC`: 
![mvc构成图示](https://p.pstatp.com/origin/fe6e00011afc515495cb)

`MVVM`:是前端视图层的开发思想，主要把每个页面分成了M、V、vm，其中，vm是mvvm的思想核心，因为vm是我们m跟v的调度者
![mvvm构成及前后端是怎么传数据的](https://p.pstatp.com/origin/fe2d00011a614b5a6433)

## vue的基本代码以及mvvm之间的对应

> 代码


```html
<div id="app">
	<p>{{ msg }}</p>
</div>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
	// 创建vue实例
	//当我们导入包之后，在浏览器内存中，就多了个vue构造函数
	var vm = new Vue({
		el: '#app', //vue实例控制页面哪个区域
		data:{
			//存放的是el中的数据
			msg: '存放学习VUE' //通过vue提供的指令很方便的渲染到页面上，程序员不再手动操作dom元素了[前端的vue之类的框架。不提倡我们手动去操作dom]
		}	
	})
</script>
```
> 代码截图

![vue mvvm结构](https://p.pstatp.com/origin/fef800008fd03d5c14a1)