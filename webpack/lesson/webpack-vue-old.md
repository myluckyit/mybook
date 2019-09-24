# webpack的使用

## 一、初始化package.json文件

```
	npm init 
```

## 二、全局安装 webpack、webpack-cli

```
	npm i webpack webpack-cli -g
	or
	cnpm i webpack webpack-cli -g
``

**注意：如果 webpack 安装在全局，那么 CLI 也需要装在全局**

i是install的缩写，-D是--save-dev的缩写

## 三、在src目录中创建index.html和index.js

1、在package.json中增加build命令

```
	"script":{
		"build":"webpack"
	}
```

index.js

```
	console.log("入口文件")
```

2、执行打包命令

```
	npm run build
```

## 四、安装vue、vue-loader(用于解析vue文件)

```
	cnpm i vue vue-loader -D
```

## 五、新建App.vue文件

```
	App.vue文件
	
	<template>
		<div id="app">
			{{msg}}
		</div>
	</template>
	
	<script>
		export default {
			data(){
				return {				
					msg:"hello world!"
				}
			}
		}
	</script>
```

```
	index.js文件
	
	console.log("入口文件");
	import Vue from "vue"
	import App from "./App.vue"
	
	
	new Vue({
		el:"#root",
		render:h=>h(App)
	})
```

## 六、在项目根目录创建webpack.config.js文件

```
	webpack.config.js文件
	
	const path = require('path')
	//引入vue-loader插件
	const VueLoaderPlugin = require('vue-loader/lib/plugin')
	
	module.exports = {
		mode:"production",//模式 ,production生产模式，development开发模式
		module:{			//模块读取
			rules:[			//定义文件读取规则
				{
					test:/\.vue$/,
					loader:'vue-loader' //文件对应的读取器
				}
			]
		},
		plugins:[  //使用插件
			new VueLoaderPlugin()
		]
	}

```

此时运行npm run build，会报错。
再在项目中按钮webpack和webpack-cli即可
```
	npm i webpack webpack-cli -D
	or
	cnpm i webpack webpack-cli -D
```
运行npm run build即可打包成功

## 七、配置开发模式

1、修改package.json文件的运行命令

```
	"scripts":{
		"serve":"webpack-dev-server --mode development --open",
		"build":"webpack --mode production"
	}
```

2、安装webpack-dev-server

```
	npm i webpack-dev-server -D
```

3、配置webpac.config.js参数

安装：html-webpack-plugin

```
	cnpm i -D html-webpack-plugin
```

```
	// 引入模块
	const path = require('path')    
	const webpack = require("webpack");
	const HtmlWebPackPlugin = require("html-webpack-plugin");   
	const VueLoaderPlugin = require('vue-loader/lib/plugin')    
	
	module.exports = {
	    mode: 'development',
	    entry:{
	        index:'./src/index.js',
	    },
	    output:{
	        path:path.resolve(__dirname,'dist'),
	        filename:'[name].bundle.js'
	    },
	    module: {
	        rules: [
	        {
	            test: /\.vue$/,
	            loader: 'vue-loader'
	        },
	        ]
	    },
	    // 使用插件
	    plugins: [
	        new HtmlWebPackPlugin({
	            title:'webpack项目',
	            template:'./src/index.html',
	            filename:'index.html',
	        }),
	        new VueLoaderPlugin()
	    ],
	    devServer: {
	        contentBase: path.join(__dirname, "src"),  //选择服务器路径,即服务器根目录选择
	        compress: true,         
	        port: 8033,             //端口
	        host: "127.0.0.1",      //服务器的ip地址
	    }
	}

```

### 八、热更新

在webpack.config.js中引入webpack模块

const webpack=require('webpack');


添加插件
```
	plugins:[
	    new HtmlWebPackPlugin({
	        title:'略略略',
	        template:'./src/index.html',
	        filename:'index.html',
	    }),
	    new webpack.HotModuleReplacementPlugin()    //引入热更新插件
	]
```
配置devServer参数

```
	devServer:{
	    host:'localhost',   //服务器的ip地址
	    port:1573,  //端口
	    open:true,  //自动打开页面，
	    hot:true,   //开启热更新
	}
```

## 九、css-loader 和 sass-loader
先安装：

```
    npm i css-loader node-sass style-loader sass-loader vue-style-loader -D
```

然后在rules规则中加入： 注意，vue-style-loader要放在前面

```
	{
	    test: /\.css$/,
	    use:['vue-style-loader','css-loader']
	    },
	{
	    test: /\.scss$/,
	    use: [
	        'vue-style-loader',
	        'css-loader',
	        'sass-loader'
	    ],
	},
```
将css样式单独抽离成文件
webpack4.0 版本下 使用 mini-css-extract-plugin

引入后再rules中加入：

```
	{
	    test: /\.css$/,
	    use: [
	        MiniCssExtractPlugin.loader,
	        // 'vue-style-loader', 
	        'css-loader',
	    ],
	    exclude: /node_modules/,              // 排除
	    include: /src/,
	},
	{
	    test: /\.scss$/,
	    use: [
	        'vue-style-loader',
	        'css-loader',
	        'sass-loader'
	    ],
	    exclude: /node_modules/,              // 排除
	    include: /src/,
	},
```
mini-css-extract-plugin貌似可以直接取替vue-style-loader

## 十、webpack4下的babel 7.x
安装：

webpack 4.x + babel-loader 8.x + babel 7.x
```	
	npm install -D babel-loader @babel/core @babel/preset-env webpack
```

webpack 4.x + babel-loader 7.x + babel 6.x
```
	npm install -D babel-loader@7 babel-core babel-preset-env webpack
```

在配置文件中的 rules加入：

```
	{
	    test: /\.js$/,
	    loader: 'babel-loader',
	    include: /src/
	}
```
