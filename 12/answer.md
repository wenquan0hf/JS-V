## 简答题
###### 一、参考答案
sticky 属性反映了搜索是否具有粘性（ 仅从正则表达式的 lastIndex 属性表示的索引处搜索 ）。sticky 是正则表达式对象的只读属性。

```js
var str1 = 'table football';
var regex1 = new RegExp('foo','y');

regex1.lastIndex = 6;

console.log(regex1.sticky);
// expected output: true

console.log(regex1.test(str1));
// expected output: true

console.log(regex1.test(str1));
// expected output: false
```

参考链接 <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/sticky>

## 编程题

###### 一、参考答案
```js
/\p{Unified_Ideograph}/u
```

参考文章 <https://zhuanlan.zhihu.com/p/33335629>

###### 二、参考答案
```js
/^([0-9]|1[0-2])$/
```

###### 三、参考答案
```js
str.replace(/\b[^a ]/gi, 'b');
```
