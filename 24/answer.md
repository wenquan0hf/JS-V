## 简答题

###### 一、参考答案
用 extends 不能实现多继承。

## 编程题

###### 一、参考答案

```js
class SimpleArray extends Array {
  constructor() {
    super();
  }

  difference(arr) {
    return this.filter(x => !arr.includes(x));
  }
}
```

使用 es5 继承 Array 时，情况比较复杂，不同的环境现象也不一样，参考文章 <http://perfectionkills.com/how-ecmascript-5-still-does-not-allow-to-subclass-an-array/>