# call、apply和bind的区别

call、apply和bind都可以改变函数this的指向。

## 实例一

```js
	var a = 1;
	var obj = {
		a:2,
		getA:function(){
			return this.a
		}
	}
	
	obj.getA();//2
	var getA1 = obj.getA;
	// getA在外部调用，此时的this指向了全局对象
	getA1();//1
	
	为了保证this指向不变，我们可以通过bind方法绑定this指向
	如：
		var getA2 = obj.getA.bind(obj);
		console.log(getA2()); //2
	
	此时可以看到this的指向保持指向了obj这个对象。
	用call/apply方法来保证this指向obj这个对象如下：
		var getA3 = obj.getA.call(obj);
		console.log(getA3); //2
		var getA4 = obj.getA.apply(obj);
		console.log(getA4); //2
		
	此时你会发现当我们用call或者apply方法来保证this指向的时候，
	call和apply方法会直接执行掉getA这个方法。
	
```

## 实例二

```
	var obj = {
		a:2,
		sum:function(b,c){
			return this.a + b + c;
		}
	}
	
	var sum0 = obj.sum;
	
	//分别用bind，call，apply方法来调用sum0方法。
	var sum1 = sum0.bind(obj,2,3);
	console.log(sum1()); // 7
	
	var sum2 = sum0.call(obj,2,3);
	console.log(sum2); // 7
	
	var sum3 = sum0.apply(obj,[2,3]);
	console.log(sum3); // 7
	
	从这里我们可以看出bind和call方法传入参数方式和apply方式不一样。
	
```


## 总结

**bind和call，apply的区别**

1.bind只会改变函数this指向不会执行函数，call和apply会改变this指向并且直接执行了函数。

2.call和bind方法可以传入多个参数，第二个参数后的所有参数都传入调用的函数中，apply方法只能传入两个参数，且第二参数为数组，数组里面的元素传入到调用的函数中。


