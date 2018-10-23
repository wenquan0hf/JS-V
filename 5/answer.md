## 简答题

###### 一、参考答案：
输出 `2`，因为 `switch...case` 是严格比较的，即使用 `===` 比较。

###### 二、参考答案：
`throw` 用来抛出一个用户自定义的异常。当前函数的执行将被停止（throw之后的语句将不会执行），并且控制将被传递到调用堆栈中的第一个catch块。如果调用者函数中没有catch块，程序将会终止。

```js
function getRectArea(width, height) {
  if (isNaN(width) || isNaN(height)) {
    throw "Parameter is not a number!";
  }
}

try {
  getRectArea(3, 'A');
}
catch(e) {
  console.log(e);
  // expected output: "Parameter is not a number!"
}
```
参考链接：<https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/throw>


###### 三、参考答案：

1. `message`：错误消息
2. `name`：错误名称

还有一些非标准的属性，比如 IE 浏览器：

1. `description`：等同于 `message`。
2. `number`：错误编号。

比如 FF 浏览器：

1. `fileName`：文件名
2. `lineNumber`：发生错误的行号
3. `columnNumber`：发生错误的列号
4. `stack`：发生错误时的程序调用栈

参考链接：<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error>


## 编程题

###### 一、参考答案
```js
var num = 10000;
var year = 1;
while (true) {
  num = num + num * 0.08 - 1000;
  if (num < 0) {
    console.log(year);
    break;
  }
  year++;
}
```
###### 二、参考答案

```js
for (var row = 1; row <= 9; row++) {
  var chart = '';
  for (var col = 1; col <= row; col++) {
    chart += `${col}*${row}=${col * row}`;
    if (col < row) {
      chart += ' '.repeat(4);
    }
  }
  console.log(' '.repeat(4 * (10 - col)) + chart);
}
```