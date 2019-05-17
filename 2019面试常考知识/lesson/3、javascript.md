# javascript

11 cookies，sessionStorage和localStorage的区别？

```
	共同点：都是保存在浏览器端，且是同源的。
	
	区别：
		1、cookies是为了标识用户身份而存储在用户本地终端上的数据，始终在同源http请求中携带，
			即cookies在浏览器和服务器间来回传递，而sessionstorage和localstorage不会自动把数据
			发给服务器，仅在本地保存。
		2、存储大小的限制不同。cookie保存的数据很小，不能超过4k，而sessionstorage和
			localstorage保存的数据大，可达到5M。
		3、数据的有效期不同。cookie在设置的cookie过期时间之前一直有效，即使窗口或者浏览器关闭。
			sessionstorage仅在浏览器窗口关闭之前有效。localstorage始终有效，窗口和浏览器关闭也一
			直保存，用作长久数据保存。
		4、作用域不同。cookie在所有的同源窗口都是共享；sessionstorage不在不同的浏览器共享，即
			使同一页面；localstorage在所有同源窗口都是共享
```
