---
title: 'vue-resourse 实现get,post,jsonp请求'
tags: vue
categories: Vue
top_img: http://p1.qhimg.com/bdr/__85/t016e6b45a49dfa2b80.jpg
cover: https://5b0988e595225.cdn.sohucs.com/images/20180621/55a7c22bc6ae4debb81c34367837460d.jpeg
comments: false
abbrlink: 2976
date: 2020-05-28 14:17:46
top:
indexing:
---
## vue-resourse 

> CDN引用地址：https://cdn.jsdelivr.net/npm/vue-resource@1.5.1

* get请求地址：http://jsonplaceholder.typicode.com/users
* post请求地址：http://jsonplaceholder.typicode.com/users
* jsonp请求地址：http://jsonplaceholder.typicode.com/users

## code
```
		<div id="app">
			<input type="button" name="" value="get请求" @click="getInfo">
			<input type="button" name="" value="post请求" @click="postInfo">
			<input type="button" name="" value="jsonp请求" @click="jsonpInfo">
		</div>
		<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
		<!-- vue-resource依赖于vue -->
		<!-- this.$http.get / post /jsonp -->
		<script src="https://cdn.jsdelivr.net/npm/vue-resource@1.5.1"></script>
		<script type="text/javascript">
			var vm = new Vue({
				el:'#app',
				data:{

				},
				methods:{
					getInfo:function () {
						// 当发起get请求之后通过 .then设置成功的回调函数
						this.$http.get('http://jsonplaceholder.typicode.com/users').then(result=>{
							// sucess callback
							console.log(result.body)
						},result=>{
							//error callback
						})
					},
					postInfo:function(){
						this.$http.post('http://jsonplaceholder.typicode.com/users',{},{ emulateJSON : true }).then(result=>{
							console.log(result.body)
						})
					},
					jsonpInfo:function(){
						// 发起jsonp请求
						this.$http.jsonp('http://jsonplaceholder.typicode.com/users').then(function(result){
							console.log(result.body)
						})
					}
				},
			})
		</script>
```
## 截图
![控制台请求结果](https://ae01.alicdn.com/kf/Hcabbdf75602f4b8a8e73352a861fa8d4L.jpg)

## 演示：

[点击演示](/file/vue-resource.html)

### get
```vue
this.http.get('/someUrl', [config]).then(successCallback, errorCallback);
```
### post
```vue
this.$http.post('/someUrl', [body], [config]).then(successCallback, errorCallback);
```
**注意**
发起post请求格式：*application/x-wwww-form,-urlencodeed*
手动发起的post请求，默认没有表单格式，有的服务器处理不了 
这里需要添加`config` 属性 `emulateHTTP`

详见：https://github.com/pagekit/vue-resource/blob/develop/docs/http.md

### jsonp
```vue
jsonp('url', [config]).then(successCallback, errorCallback);
```