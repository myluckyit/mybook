# webpack搭建vue脚手架

## 一、创建项目基本结构

1. 创建一个项目名为vue-webpack-cli
2. 在项目根目录中创建src文件，在src文件下创建如下文件：

src/app.vue

```
	<template>
		<div id="app">
			<h>{{msg}}</h>
		</div>
	</template>
	
	<script>
		export default {
			data(){
				return {
					msg: "hello vue!"
				}
			}
		}
	</script>

```

src/index.html

```html
	<body>
		<div id="app"></div>
	</body>
```

src/main.js

```js
	//vue入口文件
	import Vue from 'vue'
	import App from './app.vue'
	
	new Vue({
		el: "#app",
		render: h=>h(App)
	})

```

## 二、在项目根目录中创建package.json文件

```
	npm init -y
```

## 三、在项目根目录下下载vue, vue-loader

```
npm i vue vue-loader html-webpack-plugin --save-dev
```

## 四、在项目根目录下创建webpack.config.js文件

```
	webpack.config.js文件
	
	const path = require('path')
	const webpack = require("webpack")
	//引入vue-loader插件
	const VueLoaderPlugin = require('vue-loader/lib/plugin')
	//解析HTML
	const htmlWebpackPlugin = require("html-webpack-plugin")
	
	module.exports = {
		entry: {
			main: "./src/main.js"
		},
		module:{			//模块读取
			rules:[			//定义文件读取规则
				{
					test:/\.vue$/,
					loader:'vue-loader' //文件对应的读取器
				}
			]
		},
		plugins:[  //使用插件
			new webpack.HotModuleReplacementPlugin(),
			new VueLoaderPlugin(),
			new htmlWebpackPlugin({
				template: "./src/index.html"
			})
		],
		devServer: {
			contentBase: path.resolve(__dirname,"./src"),
			host: "localhost",
			port: 9090,
			compress: true,
			hot: true,
			open: true	//执行命令自动打开浏览器
		}
	}

```

## 五、打开package.json文件进行入下配置：

```
{
	"scripts": {
    	"serve": "webpack-dev-server --mode=development", 	//开发模式
    	"build": "webpack --mode=production"				// 生产模式
  	}
}
```

此时运行npm run serve，会报错。
再在项目中按钮webpack和webpack-cli即可
以及vue-template-compiler.
```
	npm i webpack webpack-cli vue-template-compiler -D
	or
	cnpm i webpack webpack-cli vue-template-compiler -D
```

运行npm run serve即可在浏览器中打开localhost:9090
（注意：不行的话，把node_modules文件删除，重新下载所有依赖即可）

## 六、解析vue中的css

1. 下载vue-style-loader, css-loader.

```
	npm i vue-style-loader css-loader
```

2. 在webpack.config.js中添加如下配置

```
{
	module: {
		rules: [
			{
				test: /\.css$/,
				use: [
					"vue-style-loader",
					"css-loader"
				]
			}
		]
	]
}
```

## 七、解析vue中的scss

1. 下载sass-loader, node-sass

```
	npm i sass-loader, node-sass
```

2. 在webpack.config.js中添加如下配置

```
module: {
		rules: [
			//定义scss的匹配规则
			{
				test: /\.scss$/,
				use: [
					"vue-style-loader",
					"css-loader",
					"sass-loader"
				]
			}
		]
}

```

## 八、babel配置

1. 下载对应loader

```
npm install -D babel-loader@7 babel-core babel-preset-env
```

2. 在webpack.config.js中添加如下配置

```
module: {
		rules: [
			//babel规则
			{
				test:/\.js$/,
				use: ['babel-loader'],
    			include: /src/
			}
		]
}
```

# 九、定义图片匹配规则

1. 下载

```
npm i url-loader file-loader -D
```

2. 在webpack.config.js中添加如下配置

```
module: {
		rules: [
			//babel规则
			{
				test: /\.(jpg|png|gif|svg|jpeg)/,
				use: [
					{
						loader: "url-loader",
						loader: "file-loader",
						options: {
							limit: 1024 //限制图片大小
						}
					}
				]
			}
		]
}
```

