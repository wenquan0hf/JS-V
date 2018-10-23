## 简答题

###### 一、参考答案
这个问题有人在 twitter 上面问过作者，是因为当时只给了他11天时间来创造 JavaScript，时间不够。

###### 二、参考答案
有效。是嵌套的语句块。

###### 三、参考答案
无效。switch 中的所有 case 在同个块级作用域中，可以加 {} 隔离。
```js
function func(type, value) {
  switch (type) {
    case 'square': {
        const result = Math.pow(value, 2);
        return result;
      }
    case 'cubic': {
      const result = Math.pow(value, 3);
      return result;
    }
    default:
      break;
  }
}

func('cubic');
```

###### 四、参考答案
输出 3。当执行函数时，循环已经运行结束，此时 i 的变量值是 3。

###### 五、参考答案
输出 1.3。当执行函数时，执行栈中已经有 `myFloat` 变量并且它的值也已经初始化为 1.3，函数是可以访问这个变量的。

###### 六、参考答案
输出 8。return 后面的函数是会提升到 return 语句之前的，相当于下面的代码：

```js
function foo(){
  function bar() {
    return 3;
  }
  function bar() {
    return 8;
  }
  return bar();
}
console.log(foo());
```


## 编程题

###### 一、参考答案

```js
function gen(startValue) {
  return function () {
    startValue += 1;
    return startValue;
  };
}
const genInteger = gen(100);
```

###### 二、参考答案
```js
// 使用 bind
function f() {
  var result = [];
  for (var i = 0; i < 3; i++) {
    var func = function (value) {
      return value;
    }.bind(null, i);
    result.push(func);
  }
  return result;
}

console.log(f()[0]());

// 或者使用 let
function f() {
  var result = [];
  for (let i = 0; i < 3; i++) {
    var func = function () {
      return i;
    };
    result.push(func);
  }
  return result;
}

console.log(f()[1]());

// 使用闭包

function f() {
  var result = [];
  for (var i = 0; i < 3; i++) {
    var func = (function (value) {
      return function() {
        return value;
      };
    })(i);
    result.push(func);
  }
  return result;
}

console.log(f()[1]());
```