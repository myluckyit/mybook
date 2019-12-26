# 什么是nodejs？

简单的说 Node.js 就是运行在服务端的 JavaScript。

Node.js 是一个基于Chrome JavaScript 运行时建立的一个平台。

Node.js是一个事件驱动I/O服务端JavaScript环境，基于Google的V8引擎，V8引擎执行Javascript的速度非常快，性能非常好。

V8引擎本身就是用于谷歌浏览器的js解释部分，但是Ryan Dahl鬼才般的将V8搬到了服务器，用于做服务器的软件。

## 适合开发什么？

nodejs适合用于开发什么样的应用程序呢？
	善于I/O，不善于计算，因为nodejs最擅长的就是人物调度，如果你的业务有很多的CPU计算，实际上也相当于这个计算阻塞了这个单线程，就不适合node开发。
	当应用程序需要处理大量并发I/O，而在客户端发出响应之前，应用程序内部并不需要进行非常复杂的处理的时候，nodejs非常适合，nodejs也非常适合于web socket配合，开发长链接的实时交互应用程序。

比如：
	用户表单收集
	考试系统
	聊天室
	图文直播
	提供json的api


	
	
	