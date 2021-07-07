---
title: "js小项目-贪吃\U0001F40D"
tags: javascript
categories: Web前端
top_img: 'http://p1.qhimg.com/bdr/__85/t01f2397475af482659.jpg'
cover: >-
  https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2381468826,3029522659&fm=11&gp=0.jpg
abbrlink: 40432
date: 2020-07-27 20:50:56
comments:
top:
indexing:
---

# Tools对象
```javascript
	(function(){
		var Tools = {
			getRandom: function (min,max) {
				// body...
				return Math.floor(Math.random() * (max - min + 1)) + min;
			}
		};
		// 暴漏tools给window
		window.Tools = Tools;
	})()
```

# Food对象
```javascript
	/*
	Food对象: 

		属性：x,y.width,height,color

		方法： render 随机生成对象，并输出在map上

	*/

	// function fn(){
	// 	// 局部作用域
	// 	var n = 1;
	// }
	// fn()

	// 优化：
	// 		使用自调用函数
	(function(){

		// 局部作用域：避免作用域命名冲突 

		var position = 'absolute';

		// 定义上一次食物的位置，便于删除

		var elements = [];

		function Food(options){
			// 确认对象是否null
			options = options || {};
			this.x = options.x || 0;
			this.y = options.y || 0;

			this.width = options.width || 20;
			this.height = options.height || 20;

			this.color = options.color || 'green';
		}

		// 渲染
		Food.prototype.render = function(map) {
			// body...
			
			// 三、 删除之前创建的食物

			remove()

			// 二、随机设置 x , y 的随机位置
			// 分析：
				// 1.先确定页面到底能够放几个食物
				// 2. 思路：
						// 调用工具对象方法
					 	// map容器width(height) / 食物的width(height) - 1
			this.x = Tools.getRandom(0,map.offsetWidth/this.width - 1) * this.width;
			this.y = Tools.getRandom(0,map.offsetHeight/this.height - 1) * this.height;
			

			// 一、动态创建食物显示在页面

			var div = document.createElement('div');
			map.appendChild(div);
			elements.push(div);
			// 设置div样式
			div.style.position = position;
			div.style.left = this.x + 'px';
			div.style.top = this.y + 'px';
			div.style.width = this.width + 'px';
			div.style.height = this.height + 'px';
			div.style.backgroundColor = this.color;
		};

		function remove(){
			for (var i = elements.length - 1; i >= 0; i--) {
				// 倒着删除div ，好处：不改变索引
				elements[i].parentNode.removeChild(elements[i])
				// 删除数组中元素
				elements.splice(i,1);
			}	
		}


		// 把Food构造函数让外部可以访问
		window.Food = Food;
	})()


	// 测试
	// var map = document.getElementById('map')
	// var f = new Food()
	// f.render(map)
```

# Snake对象
```javascript
	/*
		
		Snake 对象分析：

			属性： width,height,body(🐍头,🐍身),direction

			方法： render 随机生成对象，并输出在map上

	*/
	// 创建局部作用域
	(function(){
		var position = 'absolute';
		// 创建之前的🐍
		var elements = [];
		function Snake(options){
			options = options || {};
			// 🐍节大小
			this.width = options.width || 20;
			this.height = options.height || 20;
			// 🐍节方向
			this.direction = options.direction ||  'right';
			// 🐍节 (头+身子)
			this.body = [
				{x : 3, y : 2, color: 'red'},
				{x : 2, y : 2, color: 'blue'},
				{x : 1, y : 2, color: 'blue'},
			];
		}
		Snake.prototype.render = function(map) {
			// body...
			// 🐍节渲染到map上

			// move之前分析： 必须移除之前的🐍
			remove();

			for(var i = 0, len = this.body.length; i < len; i++){
				// 🐍节渲染出来了
				var obj = this.body[i];
				var div = document.createElement('div');
				map.appendChild(div);
				elements.push(div);
				// 脱离文档流
				div.style.position = position;
				div.style.width = this.width + 'px';
				div.style.height = this.height + 'px';
				div.style.left = obj.x * this.width + 'px';
				div.style.top = obj.y * this.height + 'px';
				div.style.backgroundColor = obj.color;
			}
		};


		// 创建私有成员remove()
		function remove(){
			for (var i = elements.length - 1; i >= 0; i--) {
				// 删除🐍div
				elements[i].parentNode.removeChild(elements[i]);
				// 删除数组中的元素
				elements.splice(i,1)
			}
		}


		// 控制🐍移动的方法

		Snake.prototype.move = function(food,map) {
			// body...
			// 1.控制🐍身体移动（当前🐍节到上一个🐍节的位置）
			for (var i = this.body.length - 1; i > 0; i--) {
				this.body[i].x = this.body[i - 1].x;
				this.body[i].y = this.body[i - 1].y;
			}
			// 2.控制🐍头移动
			// 判断🐍移动方向
			var head = this.body[0];
			switch(this.direction){
				case 'right':
					head.x += 1;
					break;
				case 'left':
					head.x -= 1;
					break;
				case 'top':
					head.y -= 1;
					break;
				case 'bottom':
					head.y += 1;
					break;
			}
			//3.判断🐍头是否跟食物坐标重合
			var headX = head.x * this.width;
			var headY = head.y * this.height;
			if (headX === food.x && headY === food.y) {
				// 让🐍加一节
				// 思路：
						// 获取🐍的最后一节 ，增加一节
				var last = this.body[this.body.length-1];
				this.body.push({
					x: last.x,
					y: last.y,
					color: last.color
				});

				// 在地图上重新生成食物
				food.render(map);
			}
		};


		// 暴露
		window.Snake = Snake;
	})()
	// 测试
	// var map = document.getElementById('map')
	// var s = new Snake();
	// s.render(map)
```
# Game对象
```javascript
	/*

		Game对象分析：

			属性： food , snake , map 

			方法： start 开始游戏 =>（绘制所有游戏对象）
		
	*/ 

	// 创建局部作用域避免命名冲突

	(function(){
		var that;  //记录游戏对象
		function Game(map){
			this.food = new Food();
			this.snake = new Snake();
			this.map = map;
			that = this;
		}

		Game.prototype.start = function() {
			// body...

			// 一、把 🐍 和食物对象渲染到地图上
			this.food.render(this.map);
			this.snake.render(this.map);

			// 测试 🐍 的移动
			// this.snake.move();
			// this.snake.render(this.map);
			// this.snake.move();
			// this.snake.render(this.map);
			

			// 二、开始游戏逻辑

			// 1. 让🐍移动起来 【定时器】

			runSnake();

			// 2. 通过键盘控制🐍移动	

			// 改变🐍direction方向
			bindKey();
			// 3. 当遇到 食物 做相应的处理

			// 寻找move方法

			// 4. 当🐍遇到边界就 死  了~ gameover 拜拜了你老！！！
			
	 	}


	 	// 注册键盘事件
	 	function bindKey(){
	 		document.addEventListener('keydown',function(e){
	 			// console.log(e.keyCode);
	 			/*
					上： 38
					下： 40
					左： 37
					右： 39
	 			*/ 
	 			switch(e.keyCode){
	 				case 37:
	 					that.snake.direction = 'left';
	 					break;
	 				case 38:
	 					that.snake.direction = 'top';
	 					break;
	 				case 39:
	 					that.snake.direction = 'right';
	 					break;
	 				case 40:
	 					that.snake.direction = 'bottom';
	 					break;
	 			}
	 		})
	 	}

	 	// 创建私有函数让🐍动起来
	 	function runSnake(){
	 		var timerId = setInterval(function(){
	 			// 让🐍走一格

	 			// 定时器对象指向window 我们需要寻找Game对象里的Snake
	 			that.snake.move(that.food,that.map);
	 			that.snake.render(that.map);


	 			//  当🐍遇到边界的游戏结果

	 			// 获取🐍头的坐标
	 			var maxX = that.map.offsetWidth / that.snake.width;
	 			var maxY = that.map.offsetHeight / that.snake.height;
	 			var headX = that.snake.body[0].x;
	 			var headY = that.snake.body[0].y;
	 			if (headX < 0 || headX >= maxX) {
	 				alert('Game OVER! 你死了你死了听见没有');
	 				clearInterval(timerId);
	 			}
	 			if (headY < 0 || headY >= maxY) {
	 				alert('Game OVER! 你死了你死了听见没有');
	 				clearInterval(timerId);
	 			}

	 		},150)
	 		
	 		/*
				
				bind并没有调用方法而是起到指向作用
			
	 		*/ 

	 		// var timerId = setInterval(function(){
	 		// 	// 让🐍走一格

	 		// 	// 定时器对象指向window 我们需要寻找Game对象里的Snake
	 		// 	this.snake.move(this.food,this.map);
	 		// 	this.snake.render(this.map);


	 		// 	//  当🐍遇到边界的游戏结果
	 			
	 		// 	// 获取🐍头的坐标
	 		// 	var maxX = this.map.offsetWidth / this.snake.width;
	 		// 	var maxY = this.map.offsetHeight / this.snake.height;
	 		// 	var headX = this.snake.body[0].x;
	 		// 	var headY = this.snake.body[0].y;
	 		// 	if (headX < 0 || headX >= maxX) {
	 		// 		alert('Game OVER! 你死了你死了听见没有');
	 		// 		clearInterval(timerId);
	 		// 	}
	 		// 	if (headY < 0 || headY >= maxY) {
	 		// 		alert('Game OVER! 你死了你死了听见没有');
	 		// 		clearInterval(timerId);
	 		// 	}

	 		// }.bind(that),150)
	 	}

		// 暴漏构造函数
		window.Game = Game;
	})();

	// // 测试
	// var map = document.getElementById('map');
	// var game = new Game(map);
	// game.start();
```

# Main 对象
```javascript
	/*
		Author: Dong
		QQ: 1160240060
		Project: 贪吃🐍
		依赖关系： 
			Food -> Tools
			Game -> Smake + Food
			Main -> Game
		Github： https://www.github.com/jdkq/
	*/ 

	(function(){
		var map = document.getElementById('map');
		var game = new Game(map);
		game.start();
	})()
```

# 页面
```html
	<!DOCTYPE html>
	<html>
	<head>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width,initial-scale=1.0">
		<link rel="stylesheet" type="text/css" href="./css/style.css">
		<title>贪吃蛇</title>
	</head>
	<body>
		<div id="map"></div>
		<script type="text/javascript" src="./js/tools.js"></script>
		<script type="text/javascript" src="./js/food.js"></script>
		<script type="text/javascript" src="./js/snake.js"></script>
		<script type="text/javascript" src="./js/game.js"></script>
		<script type="text/javascript" src="./js/main.js"></script>
	</body>
	</html>
```

# 演示地址

[点击跳转](/snake/index.html)
