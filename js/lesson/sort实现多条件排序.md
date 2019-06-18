# sort实现多条件排序

字符串进行排序我们可以通过localeCompare()方法
```js
let arr = ["张三","王五","艾一","王埃竹"]
arr.sort(function(a,b){
    return a.localeCompare(b,'zh-CN');
})
console.log(arr)//["艾一", "王埃竹", "王五", "张三"]
```
我们指定为简体汉字 这样就不会错了. 按这个思路那么其他语言也可以排序了.

```js
const jsonStudents = [
            {name:"きあいのタスキ", totalScore:"197", Chinese:"100",math:"97"},
            {name:"あぃまさｎ", totalScore:"196",Chinese:"99", math:"97"},
            {name:"いいいぇ", totalScore:"195",Chinese:"99", math:"10"},
            {name:"いいいぇ", totalScore:"195",Chinese:"96", math:"80"},
            {name:"いいいぇ", totalScore:"185", Chinese:"88", math:"97"},
            {name:"かまでい", totalScore:"196", Chinese:"96",math:"100"},
            {name:"佐藤", totalScore:"196", Chinese:"98",math:"98"},
            {name:"高橋", totalScore:"198", Chinese:"99",math:"99"}];
            
        jsonStudents.sort(function(a,b){
            var value1 = a.name,
                value2 = b.name;
            if(value1 !== value2){
                return value1.localeCompare(value2,'ja');
            }else if(a.totalScore!== b.totalScore){
                return a.totalScore -b.totalScore;
            }else{
                return a.Chinese - b.Chinese;
            }
        })
    console.log(jsonStudents);
```

原文：https://blog.csdn.net/q970654226/article/details/82228449