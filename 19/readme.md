## 简答题

###### 一、为什么 JavaScript 没有一开始就实现块级作用域？

###### 二、下面的代码是否是有效的 JavaScript 代码？请说明原因
```js
{{{}}}
```

###### 三、下面的代码是否有语法错误，如果有，该如何修正？
```js
function func(type, value) {
  switch (type) {
    case 'square':
      const result = Math.pow(value, 2);
      return result;
    case 'cubic':
      const result = Math.pow(value, 3);
      return result;
    default:
      break;
  }
}

func('cubic');
```

###### 四、下面代码最后输出的结果是什么？请说明原因。
```js
function f() {
  var result = [];
  for (var i = 0; i < 3; i++) {
    var func = function () {
      return i;
    };
    result.push(func);
  }
  return result;
}

console.log(f()[1]());
```

###### 五、下面代码最后输出的结果是什么？请说明原因。
```js
function myFunction(myParam) {
  let myVar = 123;
  return myFloat;
}
let myFloat = 1.3;

console.log(myFunction('abc'));
```

###### 六、下面代码最后输出的结果是什么？请说明原因。
```js
var a = 1;
function b() {
  function a() {
  }
  a = 10;
  return;
}
b();
console.log(a);
```

###### 七、下面代码最后输出的结果是什么？请说明原因。
```js
function foo(){
  function bar() {
    return 3;
  }
  return bar();
  function bar() {
    return 8;
  }
}
console.log(foo());
```

## 编程题

###### 一、编写一个生成整数的函数，要求每次调用它时返回的值是上一次调用的返回值加 1，首次调用返回的值是 100。

###### 二、下面的代码，如果想使最终的输出结果为 `1`，该如何修改？请编写代码实现。

```js
function f() {
  var result = [];
  for (var i = 0; i < 3; i++) {
    var func = function () {
      return i;
    };
    result.push(func);
  }
  return result;
}

console.log(f()[1]());
```
