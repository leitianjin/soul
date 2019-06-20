---
title: Vue.js——你好世界
date: 2019-05-11 22:06:36
tags: Vue.js
cover: /img/42895346-9f853c16-8a87-11e8-99eb-e83767ef3007.png
categories: 前端开发
---



现在来看一下我们的第一个Vue.js项目，按照入门，我们来写个Hello world


首先引入vue.js文件
> 


html 示例代码：

```html
<div id="#app">
{{msg}}

</div>

```
对应的JavaScript  代码如下：

```JavaScript

var vm = new Vue({

	el : "#app",
	data : {
		msg : "hello world vue.js"
	}


})

```

