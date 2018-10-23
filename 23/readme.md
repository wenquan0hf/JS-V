## 简答题

###### 一、请简述`语法糖`的含义和由来。

###### 二、ES6 中的 Class 不支持静态属性，请简述目前业界对此的流行观点以及一些模拟实现。

###### 三、ES6 中的 Class 有提升的行为吗？请简述原因。


## 编程题

###### 一、请将下面的 ES6 代码转换成 ES5 代码。
```js
class Person {
  constructor(name) {
    this.name = name;
  }
  sayHello () {
    return 'hello ' + this.name;
  }
  static isHuman() {
    return true;
  }
}
```
