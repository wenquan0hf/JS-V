## 简答题

###### 一、使用时候应该使用 `try...catch`，请举例说明。

###### 二、Error 对象有一个非标准属性 `stack`，很多浏览器都支持这个属性，请简述这个属性的作用。

###### 三、`try...catch` 语句之后也可以跟一个 `finally` 语句块，请简述它的作用。

###### 四、如果不使用 `try...catch` 捕获异常代码，还有其他方法能捕获到代码异常的情况吗？

###### 五、 `try` 后面是否一定要有 `catch` 语句块，为什么？

###### 六、 下面代码的输出是什么，请说明原因。

```js
function func() {
  try {
    return 1;
  } catch (e) {
    console.log('catch')
  } finally {
    console.log('finally');
  }
  console.log('end');
}

console.log(func());
```

###### 七、下述代码中的 `catch` 语句块是否会执行，为什么？

```js
try {
  setTimeout(function () {
    var a = b;
  }, 1000);
} catch (e) {
  console.log(e);
}
```

###### 八、下述代码中的 `catch` 语句块是否会执行，为什么？

```js
  try {
    {{
  } catch(e) {
    console.log(e);
  }
```

## 编程题

###### 一、编写函数 `convertToObject`，将用户的输入内容转换为普通的 JavaScript 对象，请确保代码不会发生异常。
