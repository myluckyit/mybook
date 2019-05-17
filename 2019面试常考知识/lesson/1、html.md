# html常考知识汇总

1 元素的alt和title有什么异同？

```
	在alt和title同时设置的时候，alt作为图片的替代文字出现，title是图片的解释文字。
```

2 title与h1的区别、b与strong的区别、i与em的区别？

```
	title属性没有明确意义，只表示标题；h1表示层次明确的标题，对页面信息的抓取也有很大的影响
	strong标明重点内容，语气加强含义；b是无意义的视觉表示
	em表示强调文本；i是斜体，是无意义的视觉表示
	视觉样式标签：b i u s
	语义样式标签：strong em ins del code
```

3 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？

```
	行内元素：a span img input select 
	块级元素：div ul ol li dl dt dd h1 p
	空元素：<br> <hr> <link> <meta>
```

4 label的作用是什么?
```
	label标签用来定义表单控件间的关系,当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。label 中有两个属性是非常有用的, FOR和ACCESSKEY。 
	FOR属性功能：表示label标签要绑定的HTML元素，你点击这个标签的时候，所绑定的元素将获取焦点。
```

5 如何在页面上实现一个圆形的可点击区域？

```
	map+area或者svg
	border-radius
	纯js实现，一个点不在圆上的算法
```

6 实现不使用 border 画出1px高的线，在不同浏览器的Quirks mode和CSS Compat模式下都能保持同一效果

```
	<div style="height:1px;overflow:hidden;background:red"></div>
```

7 iframe框架有那些优缺点？

```
	优点：
		1、iframe能够原封不动的把嵌入的网页展现出来。
		2、如果有多个网页引用iframe，那么你只需要修改iframe的内容，就可以实现调用的每一个页面内容的更改，方便快捷。
		3、网页如果为了统一风格，头部和版本都是一样的，就可以写成一个页面，用iframe来嵌套，可以增加代码的可重用。
		4、如果遇到加载缓慢的第三方内容如图标和广告，这些问题可以由iframe来解决。
		
	缺点：
		1、搜索引擎的爬虫程序无法解读这种页面
		2、框架结构中出现各种滚动条
		3、使用框架结构时，保证设置正确的导航链接。
		4、iframe页面会增加服务器的http请求
```

8 网页验证码是干嘛的，是为了解决什么安全问题？

```
	区分用户是计算机还是人的程序;
	可以防止恶意破解密码、刷票、论坛灌水；
```

9 DOCTYPE有什么作用？标准模式与混杂模式如何区分？它们有何意义?

```
	告诉浏览器使用哪个版本的HTML规范来渲染文档。DOCTYPE不存在或形式不正确会导致HTML文档以混杂模式呈现。
	标准模式（Standards mode）以浏览器支持的最高标准运行；混杂模式（Quirks mode）中页面是一种比较宽松的向后兼容的方式显示。
```

10 HTML5为什么只需要写 <!DOCTYPE HTML>？

```
	HTML5不基于SGML（Standard Generalized Markup Language 标准通用标记语言），因此不需要对DTD（DTD 文档类型定义）进行引用，但是需要DOCTYPE来规范浏览器行为。

	HTML4.01基于SGML，所以需要引用DTD。才能告知浏览器文档所使用的文档类型，如下：
	<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
```

11 HTML5有哪些新特性,移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分HTML和HTML5

```
	新增加了图像、位置、存储、多任务等功能。
	新增元素：
	canvas
		用于媒介回放的video和audio元素
		本地离线存储。localStorage长期存储数据，浏览器关闭后数据不丢失;sessionStorage的数据在浏览器关闭后自动删除
		语意化更好的内容元素，比如 article footer header nav section
		位置API：Geolocation
		表单控件，calendar date time email url search
		新的技术：web worker(web worker是运行在后台的 JavaScript，独立于其他脚本，不会影响页面的性能。您可以继续做任何愿意做的事情：点击、选取内容等等，而此时 web worker 在后台运行) web socket
		拖放API：drag、drop
		
	移除的元素：
		纯表现的元素：basefont big center font s strike tt u
		性能较差元素：frame frameset noframes
		
	区分：
		DOCTYPE声明的方式是区分重要因素
		根据新增加的结构、功能来区分
```

12 简述一下你对HTML语义化的理解？

```
	HTML标签的语义化是指：通过使用包含语义的标签（如h1-h6）恰当地表示文档结构
	css命名的语义化是指：为html标签添加有意义的class
	
	为什么需要语义化：
		去掉样式后页面呈现清晰的结构
		盲人使用读屏器更好地阅读
		搜索引擎更好地理解页面，有利于收录
		便团队项目的可持续运作及维护
		简述一下你对HTML语义化的理解？

	用正确的标签做正确的事情。
	html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;
	即使在没有样式CSS情况下也以一种文档格式显示，并且是容易阅读的;
	搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;
	使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解
```

13 常见的浏览器内核有哪些？

```
	Trident( MSHTML )：IE MaxThon TT The World 360 搜狗浏览器
	Geckos：Netscape6及以上版本 FireFox Mozilla Suite/SeaMonkey
	Presto：Opera7及以上(Opera内核原为：Presto，现为：Blink)
	Webkit：Safari Chrome
```

14 介绍一下你对浏览器内核的理解？

```
	主要分成两部分：渲染引擎(Layout Engine或Rendering Engine)和JS引擎。
	
	渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。
	JS引擎：解析和执行javascript来实现网页的动态效果。
	
	最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。
```

------------------提高部分，不一定要会，但一定要知道以下涉及到的知识干嘛用的---------------------------

15 HTML5的文件离线储存怎么使用，工作原理是什么？

在线情况下，浏览器发现HTML头部有manifest属性，它会请求manifest文件，如果是第一次访问，
那么浏览器就会根据manifest文件的内容下载相应的资源，并进行离线存储。如果已经访问过并且
资源已经离线存储了，那么浏览器就会使用离线的资源加载页面。然后浏览器会对比新的manifest
文件与旧的manifest文件，如果文件没有发生改变，就不会做任何操作，如果文件改变了，那么就
会重新下载文件中的资源，并且进行离线存储。例如，

```
	在页面头部加入manifest属性
	
	<html manifest='cache.manifest'>
	
	在cache.manifest文件中编写离线存储的资源

	CACHE MANIFEST
	#v0.11
	CACHE:
	js/app.js
	css/style.css
	NETWORK:
	Resourse/logo.png
	FALLBACK:
	 //offline.html
	
```


16 如何实现浏览器内多个标签页之间的通信?

```
	WebSocket SharedWorker
	(WebSocket 是 HTML5 开始提供的一种在单个 TCP 连接上进行全双工通讯的协议。)
	(SharedWorker的实质在于share，不同的线程可以共享一个线程，他们的数据也是共享的。)
	
	也可以调用 localstorge、cookies 等本地存储方式。 
	localstorge 在另一个浏览上下文里被添加、修改或删除时，它都会触发一个事件，我们通过监听事件，控制它的值来进行页面信息通信。
	
	注意：Safari 在无痕模式下设置 localstorge 值时会抛出QuotaExceededError 的异常
```

17 webSocket如何兼容低浏览器？

WebSocket 是 HTML5 开始提供的一种在单个 TCP 连接上进行全双工通讯的协议。
```
	1、Adobe Flash Socket ActiveX HTMLFile (IE) 基于 multipart 编码发送 XHR 基于长轮询的 XHR
	2、引用WebSocket.js这个文件来兼容低版本浏览器。
```









