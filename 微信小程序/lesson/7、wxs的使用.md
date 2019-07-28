# wxs的使用

## 1、新建一个tools.wxs文件

```
var obj = {
  name: "小明",
  age: 12
}
var bar = function(b){
  console.log(b);
  return b
}
module.exports = {
	//必须使用键值对，不能用es6的简写
  	obj:obj,
  	bar:bar
}
```

## 2、在index.wxml中添加如下代码

```html
//1、引入tools.wxs文件
<wxs src='./../tools/tools.wxs' module="tools"></wxs>
//2、使用tools.wxs中的变量

<view>{{tools.obj.name}}</view>
<view>{{tools.obj.age}}</view>
<view>{{tools.bar(666)}}</view>
```