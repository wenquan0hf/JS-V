## 简答题

###### 一、参考答案
语法糖（Syntactic sugar），也译为糖衣语法，是由英国计算机科学家彼得·兰丁发明的一个术语，指计算机语言中添加的某种语法，这种语法对语言的功能没有影响，但是更方便程序员使用。语法糖让程序更加简洁，有更高的可读性。

参考链接 <https://zh.wikipedia.org/wiki/%E8%AF%AD%E6%B3%95%E7%B3%96>

###### 二、参考答案
赞成实现的较多，可以参考两篇讨论帖：
- <https://esdiscuss.org/topic/define-static-properties-and-prototype-properties-with-the-class-syntax>
- <https://stackoverflow.com/questions/48012663/how-to-define-a-static-property-in-the-es6-classes>

###### 三、参考答案
不能说不存在提升，类声明为提升，定义不会。

```js
// 如果不会提升，应该输出 undefined 才对，但实际上输出是: ReferenceError: Bar is not defined
console.log(typeof Bar);

class Bar {
  constructor (x) {
    this.x = x;
  }
}
```

## 编程题

###### 一、参考答案
```js
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function () {
  return 'hello ' + this.name;
}

Person.isHuman = function () {
  return true;
}
```