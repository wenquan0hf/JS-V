## 简答题

###### 一、参考答案
```js
// 方法一
data === parseInt(data, 10)

// 方法二
Number.isInteger()

// 方法三
function isInteger(value) {
  return typeof value === 'number' &&
    isFinite(value) &&
    Math.floor(value) === value;
};
```

###### 二、参考答案
`Number.isNaN` 方法不会强制把参数转为数值。

```js
Number.isNaN(undefined);  // false
Number.isNaN({});         // false
Number.isNaN('abc');   // false

isNaN(undefined);  // true
isNaN({});         // true
isNaN('abc');   // true
```

## 编程题

###### 一、参考答案
```js
function isNumber (num) {
  return typeof num === 'number' && isFinite(num);
}
// OR
function isNumber (num) {
  return Object.prototype.toString.call(num) === '[object Number]';
}
```

###### 二、参考答案
```js
function isNumeric (num) {
  return !isNaN(parseFloat(num)) && isFinite(num);
}
```

###### 三、参考答案
```js
function randomNum () {
  return Math.random() * 1000;
}
```
