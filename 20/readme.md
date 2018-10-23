## 简答题

###### 一、JavaScript 有几种创建对象的方法？

###### 二、如何创建一个没有原型的对象？

###### 三、在遍历对象的属性时，如果避免遍历到该对象的原型上面的属性？

###### 四、下面的代码是否为有效的 JavaScript？请说明原因。
```js
1..toString();
```

###### 五、下面的代码，输出是什么？请说明原因。
```js
function A() {}
function B() {}
B.prototype = new A();
let b = new B();

console.log(
  b.hasOwnProperty('constructor'),
  b.__proto__ === B.prototype,
  b.__proto__.hasOwnProperty('constructor'),
  b.__proto__.__proto__ === A.prototype,
  b.__proto__.__proto__.hasOwnProperty('constructor'),
  A.prototype.constructor === A,
  b.__proto__.__proto__.constructor === b.constructor,
  b.constructor === A
);
```

###### 六、下面的代码，输出是什么？请说明原因。
```js
var a = 10;
console.log(a.toString());
a.test = 100;
console.log(a.test);
```

###### 七、下面的代码，输出是什么？请说明原因。
```js
function A() {
  this.x = 10;
  return [1, 2, 3];
}
A.prototype.x = 8;
let a = new A();

console.log(a.x);
```


## 编程题

###### 一、请编写示例程序，演示使用原型技术实现 `Cat` 继承 `Animal` 的过程。

###### 二、请为不支持 `Object.create` 的浏览器实现类似的功能。
