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



## javascript面试题

1、说说alert的结果是多少？为什么？

```javascript
	function fn(){
		var arrFn = new Array();
		for(var i=0;i<5;i++){
			arrFn[i] = function(){
				return i;
			}
		}
		return arrFn
	}
	var box = fn();
	for(var j=0;j<box.length;j++){
		alert(box[j]())
	}
```

2、JavaScript如何实现一个类，怎么实例化这个类？

3、用工厂模式创建Person对象，有age，name属性，say()方法返回age和name的值？

4、下面这段代码，运行结果是（）

```javascript
	function test(){
		this.a = 1;
		this.b = function(){
			console.log(this.a)
		}
	}
	test.prototype = {
		b:function(){
			this.a = 2;
			console.log(this.a);
		},
		c:function(){
			this.a = 3;
			console.log(this.a)
		}
	}
	
	var mytest = new test();
	
	mytest.b(); //1
	mytest.c(); //3
	
```


// js_ajax_跨域__3_1
5、你是如何避免接口请求跨域的？


// js_数据类型__3_1
6、JavaScript的typeof返回哪些数据类型？

// js_数组_字符串__3_1
7、split()和join()的区别

// js_ajax__3_1
8、ajax请求的时候get和post方式的区别？

// js_算法__4_1

9、请按要求填写下面3道算法(不允许使用系统函数库中的函数)

（1）倒序排序字符串(输入adcy，输出ycda)
（2）将一个数字中的5替换成89，6替换成94,3替换成7,0替换成24，最后将数字做一个从大到小的排序并返回排序后的数字（如609837451将返回999887744421）
（3）判断5个数字（任意0-9）中的其中任意3个数相加是否能整除10，如果能整除则返回另两个数字的和，不能则返回-1（如3,6,4,8,8返回9；1,7,3,2,2返回-1）


// js_this问题__3_1

10、函数里的this什么含义，方法apply，call，bind的作用和区别？

// js_克隆__3_1
11、实现一个可以深度克隆对象的函数

// js_DOM操作__3_1
12、如何实现添加、移除、移动、复制、创建和查找DOM节点

// js_事件__3_1
13、什么是事件流？事件冒泡？事件捕获？事件委托？

// js_BOM__3_1
14、你如何从浏览器的url中获取查询字符串参数？

// js_协议__3_1
15、分别说说什么是http和HTTPS，端口分别是什么？

// js_ajax__3_1
16、你能熟练使用ajax吗？说说ajax的特点，并解释一下为什么要用ajax？

// js_页面优化__3_1
17、请说出，在编写前端代码时你常用的三种减少页面加载时间的方法。

//js_this__3_1
18、解释下JavaScript中this是如何工作的？

//js_promise_es6__3_1
19、es6中，promise对象有几种状态，分别是什么？

//js__3_1
20、根据下面的代码写出res运行的结果？
var hello;
var res = !!hello

//js_promise_es6__3_1
21、写出5个以上的es6新特性，并说明他们的作用。

////js_编程__3_1
22、看下面的代码，你觉得输出的结果是什么？
```js
var name = "222";
var a = {
	name:"111";
	say:function(){
		console.log(this.name);
	}
}
var fun = a.say;
fun();		//输出？
a.say();	//输出？
var b= {
	name:"333",
	say:function(func){
		func();
	}
}

b.say(a.say);//输出？
b.say = a.say;
b.say();	//输出？

```

//js_数组去重__3_1
23、封装数组去重的实现，请写出详细js代码。

//js_类型判断__3_1
24、写一段函数判断一个变量是对象还是数组？

//js_编程__3_1
25、请根据以下规律编写函数fun
fun(1).value		//1
func(1)(2).value	//5
func(1)(2)(3).value	//14

//js_逻辑__3_1
26、A、B两人分别在两座岛上。B生病了，A有B所需要的药。C有一艘小船和一个可以上锁的箱子。C愿意在A和B之间运东西，但东西只能放到箱子里。
只要箱子没被上锁，C都会偷走箱子里的东西，不管箱子里有什么。如果A和B各自有一把锁和只能开自己那把锁的钥匙，A应该如何把东西安全递交给B？

//js_编程题__3_1
27、运行一下代码，控制台输出什么？
```
var length = 10;
function fn(){
	console.log(this.length);
}
var obj = {
	length:5,
	method:function(fn){
		fn();
		arguments[0]();
	}
}
obj.method(fn,1);
```

//js_编程题__3_1
28、判断一个字符中出现次数最多的字符，asdfghfffjkflfhjffggss

// js__1_1
29、js中以下哪种方法不能弹出消息提示（）
A、alter	B、alert	C、confirm	D、prompt

// js__1_1
30、下列哪项返回false（）
A、1==parseInt('1M')	B、0==''	C、1===parseInt('1M')	D、NaN == NaN

// js__1_1
31、下列哪项返回false（）
A、1==parseInt('1M')	B、0==''	C、1===parseInt('1M')	D、NaN == NaN


// js_运算符_1_1
31、var a=10;b=20;c=5; ++b+c+a++以下哪个结果是正确的（）
A、34	B、35	C、36	D、37


// js__2_1
32、对于http://www.undata.com?q=1，location.search返回的是什么__

// js__2_1
33、原生js用___可以快速的给一个DOM节点加一段html内容。

// js__2_1
34、用____可以去除字符串var str = "0122134034"中所有的0


// js__2_1
34、求foo[5]()=_____,foo[10]=_____。
```
function Foo(){
	var result = new Array();
	for(var i=0;i<10;i++){
		result[i] = function(){
			return i;
		}
	}
	return result;
}
var foo = Foo();
```

// js__2_1
35、求（1）___，（2）___，（3）___的值

```js
(function(){
	a=10;
	console.log(a);			//（1）
	console.log(window.a);	//（2）
	var a=6;
	console.log(a);			//（3）
})()
```


// js__3_1
36、简述ECMAScirpt中基本数据类型和引用数据类型的区别。


// js_jq__3_1
37、$(this)和this关键字有何不同？


// js_定时器__4_1
37、用setTimeout模拟setInterval

// js__3_1
37、判断字符串是否是这样组成的，第一个必须是字母，后面可以是字母、数字、下划线、总长度为5-20

// js__3_1
38、截取字符串abcdefg的efg

// js_css_html__3_1
39、不同浏览器的兼容性问题，至少列举三个。

// js__3_1
40、如何规避JavaScript多人开发函数重名问题？

// js__3_1
41、JavaScript面向对象中类和类的继承如何实现？

// js_兼容性__3_1
42、FireFox下面如何实现outerHTML?

// js__4_1
43、编写一个方法，求一个字符串的字节长度

// js__4_1
44、编写一个方法，去掉一个数组的重复元素

// js__3_1
45、写出3个使用this的典型应用

// js__3_1
46、如何显示/隐藏一个DOM元素？

// js__4_1
47、JavaScript中如何检测一个变量是一个string类型？请写出函数实现


// js__4_1
48、网页中实现一个计算当年还剩多少时间的倒数计时程序，要求网页上实时动态显示“xx年还剩xx天xx时xx分xx秒

// js__4_1
49、代码实现鼠标单击Button1后将Button1移动到Button2的后面

// js__4_1
50、JavaScript有哪几种数据类型

// js__4_1
51、下面css标签在js中调用应如何拼写：border-left-color

// js__4_1
52、JavaScript中如何对一个对象进行深度clone

// js__3_1
53、如何控制alert中的换行

// js__4_1
54、请实现，鼠标点击页面中的任意标签，alert改标签的名称(注意兼容性)

// js__4_1
55、请编写一个JavaScript函数parseQueryString，他的用途是把URL参数解析为一个对象，如：
var url = "http://witmax.cn/index.php?key0=0&key1=1&key2=2"

// js_ajax__3_1
56、ajax是什么？同步和异步的区别？如何解决跨域问题？

// js_闭包__3_1
57、什么是闭包


// js_异步加载__3_1
58、请给出异步加载js方案，不少于两种


// js_动画__3_1
59、如果需要手动写动画，你认为最小事件间隔是多少？

// js_浏览器渲染__3_1
60、描述浏览器的渲染过程，

// js_类__3_1
61、JavaScript如何实现一个类，怎么实例化这个类？

// js_对象__3_1
62、用工厂模式创建Person对象，有age、name属性，say()方法返回age和name的值？

// js_对象__4_1

63、说说alert出来的结果是多少？为什么？
```js
function fn(){
	var arrFn = new Array();
	for(var i=0;i<5;i++){
		arrFn[i] = function(){
			return i;
		}
	}
	return arrFn;
}
var box = fn();
for(var j=0;j<box.length;j++){
	alert(box[j]())
}
```

// js_正则表达式__4_1

64、请写出把字符串含有空格的地方去掉的正则表达式。

// js_数组__4_1
65、数组arr=[1,2,3,4,5,6],请你写出以下操作的代码：
1）将数组中第二位元素替换为0
2）在操作后的数组的第三位元素后面增加元素8
3）删除数组的第四位元素

// js_数组__4_1
66、写出你是如何判断一个对象是否为数组，以及数组是否为空的方法？

// js_本地储存__4_1
67、列举出你所知道的浏览器本地储存方式

// js_es6__4_1
68、es6语法中的两个循环的方法

// js_es6__4_1
69、请分别写出数组和对象的解构赋值的例子

// js_es6__4_1
70、写出es6中判断两个值是否相等的方法？

// js_面向对象__4_1
71、js面向对象中实现继承有多少种方法，请列举你所知道的方法？


// js_json__4_1
72、一个json{"name":"abc","age":"18"}中怎么删除"name",使得json变为{"age":18}?

// 职业规划__3_1
73、描述你的职业规划？

// 前端框架__3_1
74、列举你熟悉的前端框架并简述他们优缺点和特点，分别适用于哪些场景？


// 前端框架_库__3_1
75、你使用过哪些JavaScript库？

// 前端框架_库__3_1
76、请描述一下cookies，sessionStorage和localStorage的区别？

// js__3_1
77、如何判断一个js对象是否存在某个属性？

// js_ajax__3_1
78、请尽可能详尽的解释ajax的工作原理

// js_ajax_跨域__3_1
79、说说js中的跨域问题，如何解决？

// js__3_1
80、"i'm a lasagna hog".split("").reverse().join("");
问题：上面的语句的返回值是什么？

// js__3_1
80、var foo = "hello";(function({var bar="World";alert(foo + bar);}))();alert(foo+bar);
问题：上面两个alert的结果是什么？

// js__3_1
81、请描述下事件冒泡机制？

// js__3_1
81、简述闭包的概念，闭包的原理。并利用闭包，写一个小段程序。

// js_MVC__3_1
82、什么是MVC，简单描述下？

// js__3_1
83、举例几个你最常浏览的网站。

// 客观题__3_1
84、请你说明下公司为何要选择你，你的独特性在哪里？

// 客观题__3_1
85、你喜爱参加什么样的集体活动？在其中你扮演什么 角色？

// 客观题__3_1
86、当你即将完成一个重要项目时，却被告知有更紧急的事情需要你去处理？你有感受如何？

//SEO_性能优化_3_1
87、请描述web前端性能优化以及SEO优化的方法，至少10个。

//SEO_性能优化_3_1
88、你对this对象的理解？

89、什么是面向对象？面向对象的特点？

90、undefined和null的区别？

91、请求下面代码输出结果是多少？为什么？
```
class Test{
	name:string = "小明",
	public constructor(){
		var fun:Function = function():void{
			console.log("name:"+this.name);
		}
		fun();
	}
}
```

92、JavaScript有哪些情况容易造成内存泄漏？
1）意外的全局变量引起的内存泄露
2）闭包引起的内存泄露
3）没有清理的DOM元素引用
4）被遗忘的定时器或者回调
5）子元素存在引起的内存泄露
6) Delete一个Object的属性会让此对象变慢（多耗费15倍的内存）

93、什么是abstract class

94、Array的sort方法采用的那种排序算法？列出你所知道的所以排序算法
```
var arrA:any[] = [{a:1},2];
var arrB:any[] = arrA.concat();
arrB[0].a = 2;arrB[1] = 1;
console.log("arrA[0].a:"+arrA[0].a); //2
console.log("arrA[1]:"+arrA[1]);	 //2
请问输出是多少？为什么？
```

95、请问下列代码最后输出多少？为什么？
```
var f = true;
if(f===true){
	var a = 10;
}
function fn(){
	var b = 20;
	c = 30;
}
fn();
console.log(a,b,c);
```

95、从0级开始强化，每强化一次，可能发生三种结果，分别叫损坏、失败、成功。
损坏指当前强化等级减一(减到0的时候不会变为负数)，失败则表示不加不减，
成功则表示加一级，满级10级。损坏、失败、成功的3个概率分别是20%，30%,50%。
请用你熟悉的代码或者伪代码模拟成功的次数。



96、什么是-Infinity，js中如何得到。

97、请写出h5有哪些新增的标签及其含义。

98、使用window.postMessage()能做什么？

99、请说一下事件冒泡和事件捕获，并给出阻止事件冒泡的方案

100、请使用js写出一段不使用循环，生成一个长度为100的数组，且每个值对应的下标。

101、谈一谈跨域，并说说如何实现express中间件代理跨域

102、下面这段代码，打印出来的是

```javascript
function test(a,b,c){
	console.log(typeof a);
	console.log(typeof b);
	console.log(typeof c);
}
test(1,"1");
```

103、下面这段代码，运行结果是
```javascript
function test(){
	this.a = 1;
	this.b = function(){
		console.log(this.a);
	}
}
test.prototype = {
	b:function(){
		this.a = 2;
		console.log(this.a);
	},
	c:function(){
		this.a = 3;
		console.log(this.a);
	}
}
var mytest = new test();
mytest.b();
mytest.c();
```

104、cookies，sessionStorage的区别？

105、new Boolean(false)?'a':'b'的结果是？为什么？



106、获取URL参数
```js
答案：
	function getQuery(){
		var name,value;
	    var str=location.href; //取得整个地址栏
	    var num=str.indexOf("?")
	    str=str.substr(num+1); //取得所有参数   stringvar.substr(start [, length ]
	
	    var arr=str.split("&"); //各个参数放到数组里
	    for(var i=0;i < arr.length;i++){
	        num=arr[i].indexOf("=");
	        if(num>0){
	             name=arr[i].substring(0,num);
	             value=arr[i].substr(num+1);
	             this[name]=value;
	        }
	    }
	    return value
	}
	console.log(getQuery())
```

107、请计算1-10000中出现0的次数
```js
答案
	function getZeroCount(num) {
	    let count=0;
	    let regObj=/0/g;
	    for (let i=1;i<=num;i++){
	        let str=''+i;
	        let match=str.match(regObj);
	        count+=match==null?0:match.length;
	    }
	    return count;
	}
	console.log(getZeroCount(10000));
	
	function getZeroCount(num) {
	    return Array.from({length: num}, (v, i) => i + 1).join().split("0").length - 1;
	}
	
	console.log(getZeroCount(10000));
```
			
108、取得函数最多传递的参数，直接调用arguments.length
```js
答案
var fun1 = function (p1, p2, p3) {
    console.log('接收的参数长度为:' + arguments.length);
    //遍历传入的参数
    for (var i in arguments) {
        //使用索引的方式获取参数值
        console.log(arguments[i]);
    }
}
console.log('fun1的参数长度为：'+fun1.length);
fun1('a', 2, 'c');

//写一个function，清除字符串前后的空格.
var str = " 123 ";
function trim(str){
	var reg = /^\s|\s$/g;
	if (str && typeof str === "string") {
        return str.replace(reg,"")
    }
}
console.log(trim(str));
```

109、对象变成数组
```js
答案
	var data={a:1,b:2,c:3};
	function toArr(obj){
        var arr1=[];
        for(var i in obj){
           arr1.push(obj[i]);
        }
        return arr1;
	}
	console.log(toArr(data));
```

110、将url的查询参数解析成字典对象

```js
答案
	function getQueryObject(url) {
	    url = url == null ? window.location.href : url;
	    var search = url.substring(url.lastIndexOf("?") + 1);
	    var obj = {};
	    var reg = /([^?&=]+)=([^?&=]*)/g;
	    search.replace(reg, function (rs, $1, $2) {
	        var name = decodeURIComponent($1);
	        var val = decodeURIComponent($2);
	        val = String(val);
	        obj[name] = val;
	        return rs;
	    });
	    return obj;
	}
    console.log(getQueryObject())
```

111、js字符串操作函数
```js
答案
//		        字符串操作函数有:
//		        	charAt() 方法可返回指定位置的字符。
//		        	concat() 方法用于连接两个或多个字符串。
//		        	indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置。
//		        	match() 方法可在字符串内检索指定的值
//		        	replace() 方法用于在字符串中用一些字符替换另一些字符
//		        	slice() 方法可提取字符串的某个部分，并以新的字符串返回被提取的部分。
//		        	split() 方法用于把一个字符串分割成字符串数组。
//		        	substr() 方法可在字符串中抽取从 start 下标开始的指定数目的字符。
//		        	trim() 去除字符串两边的空白，不改变原字符串
//		        	toUpperCase() 将字符串转化为大写
//		        	toLowerCase 方法,字符串中的字母被转换为小写字母。
```

112、怎样添加、移除、移动、复制、创建、查找Dom

```js
答案
    createElement()   //创建一个具体的元素
    createTextNode()   //创建一个文本节点
    appendChild() //添加
    removeChild() //移除
    replaceChild() //替换
    getElementsByTagName() getElementsByName() getElementById() //查找
    

    
    //写出3个使用this的典型用例
    
    1、对象方法中调用this,如果函数被当中对象的一个方法进行调用，则this值指向该对象。
    2、函数内部使用,谁调用函数,函数指向谁.
    3、new 当中进行使用,指向实例对象
```


113、下面程序输出的是什么？

```js
var myObject = {
	foo:"bar",
	func:function(){
		var self = this;
		console.log("outer func: this.foo="+this.foo);
		console.log("outer func: self.foo="+self.foo);
		(function(){
			console.log(this);
			console.log("inner func: this.foo="+this.foo)
			console.log("inner func: self.foo="+self.foo)
		})()
	}
}
myObject.func();

答案：

outer func: this.foo=bar；
outer func: self.foo=bar；
window；
inner func: this.foo=undefined；
inner func: self.foo=bar


```

114、请从2018-11-15T09:10:23 TongLew/Job中提取出结果["2018", "11", "15", "09", "10", "23"]
答案：
```js
function getNum(str){
	arr = str.split(" ");
	var res = arr[0].split(/\D/img);
	return res;
}
```


115、请对表单进行数据验证
0）去掉默认样式，并统一视觉，所有输入框不能为空值
1）手机格式正确，身份格式正确，重复密码相同
选做内容
2）表单实现响应式，适配移动端
3）地址实现省市区三级联动选择
4）生日使用兼容移动端的日历控件
5）密码要求只能有数字/字母/下划线组成，首个字符必须是字母，不能使纯数字或者纯字母，长度为8-20
6）以上限制均给出友好提示

116、为什么编写HTML时需要用到h/p/span/em/strong等等标签，而不直接使用div？

22、以下三种隐藏元素的方式有什么不同？
display:none
visibility:hidden
opacity:0

117、css3有哪些动画属性？他们之间有什么区别？

118、为什么要用事件委托？实现原理是怎么样的？

119、以下两种声明函数的形式有什么区别？
function get(){}
var get  = function(){}

120、请用元素js给下列的每个li增加点击事件，点击弹出对应li的下标
```html
<ul>
	<li>a</li?
	<li>b</li?
	<li>c</li?
</ul>
```

121、编写一个函数，返回当前年月日，格式为yyy-mm-dd

122、web应用性能优化的方法有哪些？

123、已知一段JavaScript代码如下，那么，如果在浏览器中执行这段代码，显示结果为：

```js
var str = '123456wx';
alert(str.replace(/\w$/,"y"));

```

124、已知一段JavaScript代码如下，那么，如果在浏览器中执行这段代码，显示结果为：

```
var eles = document.getElementsByTagName("div");//假设HTML中有3个div元素
for(var i=els.length-1;i>=0;i--){
	eles[i].showID = function(){
		alert(i)
	}
}
```

125、列举你所知道的设计模式？

126、用熟悉的语言实现一个单例模式？

127、JavaScript中浮点数取整有哪几种方法（写出3中以上）？

128、下面的代码能否进一步优化，有则写出优化方案？
```js
private a:number = 1;
private b:number = 1;

private myFun(n:number):number{
	for(var i:number=3;i<=n;i++){
		this.b = this.a + this.b;
		this.a = this.b-this.a
	}
	return this.b;
}
```

129、下面的代码能否进一步优化，有则写出优化方案？
```js
for(var i=0;i<arr.length;i++){
	alert(i)
}
```

130、写出程序的输出

```js
var x = 1;
function scopeTest(){
	alert(x);
	var x = 'hello world';
	alert(x);
}
scopeTest();

```

131、写出程序的输出
```js
var obj = {
	i:'test',
	m:function(){
		alert(this.i);
		function B(){
			alert(this.i);
		}
		B();
	}
}
obj.m();
```

132、http协议中和服务器交互的方法有哪些？他们之间的差别是是？

133、HTML5中和服务器通信有哪几种方式？

134、列举你所知道的在游戏开发过程中会用到的性能方面的优化？

135、浏览器页面由_、_、_三层构成

136、为确保所有h3元素不会放在左浮动元素的右边，可声明_____

137、对于http://www.urundata.com?q=1,location.search返回的是___

138、求foo[5]() = ____，foo[10]=____

```js
function Foo(){
	var result = new Array();
	for(var i=0;i<10;i++){
		result[i] = function(){
			return 1;
		}
	}
	return result;
}
var foo = Foo();
```

139、求(1)____,(2)____,(3)____的值

```js
(function(){
	a  = 10;
	console.log(a);			//(1)
	console.log(window.a);	//(2)
	var a = 6;
	console.log(a);			//(3)
})()
```

140、JavaScript的typeof返回有哪些数据类型？

141、数组方法pop()push()unshift()shift()的作用分别是？

142、代码如下，请问a和b分别是？
```js
var a=1;
b = 1;
function Fn(){
	var a=2;
	b = a;
	console.log(b);
}
fn();
console.log(a);
```

143、以下代码执行后的结果是？
```js
var t = true;
window.setTimeout(function(){
	t = false;
},1000)
while(t){};
alert('end);
```

144、以下代码输出结果是？
```js
for(var i=0;i<5;i++){
	setTimeout(function(){
		console.log(new Date,i)
	},1000)
}
```

144、作为一个前端工程师，想必你对js和jQuery并不陌生，请用代码实现以下几个问题，（js或jq都可以）

a、获取一个ID为father的节点的节点内容。

b、获取一个ID为textInpt的文本节点的文本内容，并在控制台输出。

c、简述选项卡的实现思路，可能的话附上伪代码。

145、js中支持的数据类型有__、__、__、__、__、__、__

146、js中有哪些作用域？___、___、___

147、写出下列表达式的值:

typeof null ___
isNaN('3')||0 ___
+{a:1,toString:function(){return '10'},valueOf:function(){return 100}}____


148、将字符串'hello world'转换为'dlrow olleh'可能用到的函数___,___,___

149、将一个对象保存到本地，可使用___方法将对象转换为字符串，再使用__方法保存到本地存储。

150、http请求中，设置发送数据类型的header属性为___,若要使用json类型，需要改header属性值为___

151、Git中合并代码的两种方式为__和__,若要还原代码到上一版本并清空暂存区和工作去，应使用命令___.

152、前端页面由哪三层构成，分别是什么，作用是什么？

153、split() join()的区别

154、数组方法pop() push() unshift() shift()

155、ajax请求时，如何解释json数据

156、程序运行结果是？

```js
function fn(n){
	this.a = 0;
	this.b = function(){
		alert(this.a)
	}
}
fn.prototype = {
	b:function(){
		this.a = 20;
		alert(this.a);
	},
	c:function(){
		this.a = 30;
		alert(this.a);
	}
}
var myfn = new fn();
myfn.b();
myfn.c();
```

157、介绍你最常用的框架？

158、请描述一下cookies、sessionStorage和localStorage的区别？

159、验证字符串的组成规则，第一个需要为数字，后面可以是字母，数字，下划线，总长度为5-20；

160、去掉一组整型数组重复的值[1,1,2,22,44,22,13]

161、link和@import的区别是？

162、使用js实现二叉查找树。

163、webSocket如何兼容低浏览器？

164、分别写出alert(1&&2);alert(1||2)的值。

165、不借助临时变量，进行两个整数的交换，例如：a=1.b=3.

166、web技术标准最具有影响力的组织是哪个？官网是？

167、什么是盒模型（为什么提出这个概念）？优点是什么？包括什么？

168、请用原生js编写下列程序，在浏览器显示如下：
```
	   *
	  ***
	 *****
	*******	
	 *****
	  ***
	   *
```

169、说说对跨域的理解，跨域单纯前端可以解决吗？

170、看以下2段代码，写出执行结果。

```js
for(var i=0;i<5;i++){
	(function(){
		setTimeout(function(){
			console.log(i);
		},i*1000);
	})(i);
}
结果是：
for(var i=0;i<5;i++){
	(function(i){
		setTimeout(function(){
			console.log(i);
		},i*1000);
	})(i);
}
结果是：
```

171、观察数字下列数字：
1、5、11、1、29、41......这列数中第10个数是什么？（写出你的推理过程）


172、编写一个方法，去掉数组多余的元素，使同一个元素值最多能出现两次。注意：结果要
保持元素的顺序不变，如：输入的数组[1,3,2,1,1,3]，计算后的结果为[1,3,2,1,3]

173、判断一个字符串中出现次数最多的字符，统计这个字符出现的次数，
如：字符串"abcdefgaddda",d出现次数最多，次数为4。

174、数据适配，如何把json1构成成类似json2的格式并输出到控制台，请写出思路，或者提供具体代码。
```js
var json1 = [
	{id:1,name:"广东",parentId:-1},
	{id:2,name:"深圳",parentId:1},
	{id:3,name:"广州",parentId:1},
	{id:4,name:"天河",parentId:3},
	{id:5,name:"白云",parentId:3},
]；
var json2 = {
	id:1,
	name:"广东",
	children:[
		{
			id:2,
			name:"深圳",
			children:[]
		},
		{
			id:3,
			name:"广州",
			children:[
				{
					id:4,
					name:"天河",
					children:[]
				},
				{
					id:5,
					name:"白云",
					children:[]
				}
			]
		}
	]
}

```

175、在iframe中，如何调用父窗口的方法？如果iframe嵌套不止一层？

176、jQuery选择器都有哪些，请列举出几种常用的。

177、同步异步的区别，列举场景何时应该使用同步何时应该使用异步。

178、浏览器状态码有哪些？分别是什么含义，劣迹几个常见的状态码

179、Doctype作用？严格模式与混合模式如何区分？他们有何意义？

180、通过循环递归的形式，把对象p的所有属性和方法，复制到对象c当中。

```js
答案：

function deepCopy(p,c){
	var c = c || {};
	for(var i in p){
		if(typeof p[i] === 'object'){
			c[i] = (p[i].constructor === Array) ? [] : {};
			deepCopy(p[i],c[i])
		}else{
			c[i] = p[i];
		}
	}
	retrun c;
}

```

181、已知一个数组，提供一个方法arrayStrip，去掉该数组中的所有重复元素，返回新数组，
例如：输入数组1,2,1,2,2,3，去重后输出新数组1,2,3

182、输入一个按升序排序的数组和一个数字，在数组中查找两个数，使得他们的和正好是输入的那个数字。
要求时间复杂都是o(n)。如果有多个结果，输出任意一个即可。例如：输入数组
1、2、4、7、11、15和数字15，由于4+11=15，因此输出4和11.

183、实现一个函数clone，可以对JavaScript中的5中主要的数据类型（包括number，string，object，array，Boolean）进行复制。

184、以下程序会依次输出什么内容？

```js
var foo = 1;
function(){
	console.log(foo);
	var foo = 2;
	console.log(foo);
}()
```

185、以下程序会依次输出什么内容？
```js
var user = {
	count:1,
	getCount:function(){
		return this.count;
	}
}
console.log(user.getCount());
```

186、有哪些方法可以提高页面性能?

187、你都使用哪些工具来测试代码的性能？

188、请描述一下cookies,sessionStroage和localStorage的区别？

189、HTML和XHTML有什么区别？

190、JavaScript中如何获取id为'txt'的textbox中的值？

191、如何在JavaScript声明数组？有几种方式？

192、let num = '1'+2+4;结果是？

193、let num = 3+4+'7'结果是？

194、alert(2-'1')结果是？

195、alert('6'/'2')结果是？

196、JavaScript中如何把id为'myText'的文本字体大小改为20px。

197、如何判断某变量是否为数组数据类型？

198、JavaScript如何声明类，例如声明和实例一个person类。

199、执行这段代码，输出什么结果？

```js
var fullname = 'john doe';
var obj = {
	fullname:'colin ihrig',
	prop:{
		fullname:'aurelio de rosa',
		getFullname:function(){
			return this.fullname;
		}
	}
};
console.log(obj.prop.getFullname());
var test = obj.prop.getFullname;
console.log(test());
```

200、下面这个js程序的输出是什么？
```js
function Foo(){
	var i=0;
	return function(){
		console.log(i++);
	}
}
var f1 = Foo(),f2 = Foo();
f1();
f1();
f2();
```

201、请对表单进行数据验证：（可上网查询资料）

0）去掉默认样式，并统一视觉，所有输入框不能为空值
1）手机号码格式正确，身份证格式正确，重复密码相同。
2）表单实现响应式，适配移动端
3）地址实现省市区三级联动选择
4）生日使用兼容性移动端的日历控件
5）密码要求只能由数字/字母/下划线组成，首个字符必须是字母，不能使纯数字或者纯字母，长度为8-20
6）以上限制均给出友好提示

202、把一个排行榜数据渲染到一个表格中：（可上网查询资料）
0）完成数据渲染
1）根据手机号去重
2）按照 积分进行排序，积分相同则按照时间先后排序
3）实现表格分页
4）表格样式优化（表头，奇偶行，hover）
5）可以根据手机号搜索

203、请写出一个抽奖程序（可上网查询资料）
0）实现概率：一等奖（10%）、二等奖（20%）、三等奖（30%），未中奖（40%）
1）做出简单样式，轮播闪烁奖品图片，点击按钮停止闪烁并抽奖。
选做内容：
2）实现不刷新重抽
3）实现库存：一等奖1个，二等奖2个，三等奖3个
4）采取闭包的形式对抽奖程序进行封装，并分析理由，谈谈你对闭包的理解。

204、根据给定的图片，实现一个3d立方体筛子（可上网查询资料）
0）实现3d空间里的骰子
1）骰子加上旋转动画
选做内容：
2）鼠标可拖动骰子位置
3）手指可拖动骰子位置，双指可缩放骰子大小

205、给定一个百度坐标系数组，根据用户当前位置由近到远排序，返回新的数组（可上网查询资料）


206、请根据以下规律编写函数fun

```js
fun(1).value		//1
fun(1)(2).value		//5
fun(1)(2)(3).value	//14
```


答案：

```js
var fun = function f(val){
	f.value=val;
	var init = function res(val){				
		f.value += val*val;
		res.value = f.value-1;
		return init;
	}
	return init(val);
}
```

207、JavaScript与ECMAscript的关系，及各个版本浏览器的支持情况

```
ECMAScript是标准，JavaScript是ECMAScript的一种实现，一个完整的JavaScript实现应该由以下三个部分组成：ECMAScript，DOM，BOM。
es5目前所有主流浏览器都支持，es6+目前支持情况并不是所有的浏览器都能够完美支持，其中对 ES6 新特性最友好的是 Chrome 和 Firefox 浏览器。所以用到es6+的情况下一般需要通过babel转义成es5。
```

208、原生js获取页面中所有CheckBox input的方法有哪些

```js
方法一：
document.querySelectorAll("input[type=checkbox]");

方法二：
var inputs = document.getElementsByTagName("input");
var boxs = [];
for (let i = 0; i < inputs.length; i++) {
	if (inputs[i].type == "checkbox") {
		boxs.push(inputs[i])
	}
}
console.log(boxs)
```

209、判断一个对象是数组的几种方法

```js
	1.instanceof 判断一个对象是否是由某个类型创建出来的
	
	　　obj instanceof Array = true   //则表示是数组
	2.Object.prototype.toString()方法
	
	　　Object.prototype.toString.call(arr)   == [object Array]
	
	3.Array.prototype.isPrototypeOf(obj)  //判断指定对象是否存在于另一对象的原型链中
	
	　　Array.prototype.isPrototypeOf(obj)  == true
	
	4.Obejct.getPrototypeOf(arr) == Array.prototype
	
	　　Object.getPrototypeOf(arr)== Array.prototype  //返回对象__proto__指向的原型prototype 
	
	5.最简单的方法（存在兼容）
	
	　　Array.isArray(arr) ==  true
```

210、字符串转换为整形的方法有哪些？如果将字符“abc”转换为整形，返回值是什么？

```js
字符串转换为整形：
	1. parseInt()
	2. Number()
	
返回值：NaN
```

211、call，callee，caller，apply的区别与作用

```
call(),apply(),caller(),callee()作用都是调用某个函数或方法

caller返回一个函数引用，这个函数调用了当前的函数；
使用这个属性应该注意：
	a、这个属性只有在函数执行时才有用
	b、如果在javascript程序中，函数由顶层调用的，则返回null

callee返回正在执行的函数本身的引用，他是arguments的一个属性
使用callee时应注意：
	a、这个属性只有在函数执行时才有效
	b、他有一个length属性，可以获取形参的个数，因此可以用来比较形参和实参个数是否相等，系比较arguments.length是否相等。


call(),apply()区别在于传入参数不同。
详情见：https://myluckyit.github.io/mybook/js/#/lesson/call%E5%92%8Capply%E5%8F%8Abind

```

212、在调试js过程中如何输入堆栈

213、请写出下面 //Q后面的结果

```js
var a;
			console.log(typeof a); //Q1  undefined
			a = null;
			console.log(typeof a); //Q2  object
//			console.log(b);   //Q3  报错
			
			a = new Object();
			a.value = 1;
			b = a;
			b.value = 2;
			console.log(a.value); //Q4  2
			function c(){
				console.log(a);//Q5  undefined
				var a = 2;
				console.log(a);//Q6  2
			}
			c();
```

214、看下面的代码，给出输结果

```js
for(var i=1;i<=3;i++){
	setTimeout(function(){
		console.log(i)
	},0);
}

Q1: 上述代码将输出什么？
输出3次4

Q2: 如何让上述代码输入1 2 3？
将循环中的var改为let即可，或者用闭包也可。

```

215、对作用域上下文和this的理解，看下面代码：

```js

var user = {
	count:1,
	getCount:function(){
		return this.count
	}
}
console.log(user.getCount()); //Q1 =1
var func = user.getCount;
console.log(func());		//Q2   =undefined

```

216、ajax怎么判断请求成功还是失败，原生js有没有什么方法可以代替ajax

217、看下面的代码，1.输出什么，2.foo的类型是什么？

```js
var foo = '11'+2-'1';
console.log(foo); // Q1? 111  数值类型
var foo = '11'+2+'1';
console.log(foo); //Q2? 1121  字符串类型

```

218、如何获取传入函数的所有参数（不确定参数数量）?

```
可以通过arguments来获取
```

219、直接在对象的原型上添加方法是否安全？例如在object对象上，有什么缺点

```
会导致原型污染，一般不改变默认方法执行的话，危险不是太大，
如果改变了默认方法，如果还有其他库，则可能出现未知问题。
```

220、请说明在什么情况下会考虑使用闭包或者IIFE(自执行函数)，及两者的区别？

```js
当一个函数需要用到另一个函数变量的情况下可以使用闭包，比如做选项卡效果，手风琴效果都可以用到闭包。

立即执行函数常用于第三方库，好处在于隔离作用域，任何一个第三方库都会存在大量的变量和函数，为了避免变量污染（命名冲突）
比如封装一个公共的方法的时候就用到了，用立即执行函数的目的就是避免变量污染。
```

