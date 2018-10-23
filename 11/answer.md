## 简答题

###### 一、参考答案
1. `new Date();`
2. `new Date(value);`
3. `new Date(dateString);`
4. `new Date(year, monthIndex [, day [, hours [, minutes [, seconds [, milliseconds]]]]]);`

###### 二、参考答案
```date.getFullYear() == date.getYear() + 1900```

###### 三、参考答案

```js
function diff1(date1, date2) {
  return date2 - date1;
}

function diff2(date1, date2) {
  return date2.getTime() - date1.getTime();
}

function bench(f) {
  let date1 = new Date(0);
  let date2 = new Date();

  let start = Date.now();
  for (let i = 0; i < 100000; i++) f(date1, date2);
  return Date.now() - start;
}

console.log( 'Time of diffSubtract: ' + bench(diff1) + 'ms' );
console.log( 'Time of diffGetTime: ' + bench(diff2) + 'ms' );
```

## 编程题

###### 一、参考答案

```js
/**
* 判断闰年函数
* @param  {number} year 要判断的年份
* @return {bool} 返回布尔值
*
* 其实只要满足下面几个条件即可、
* 1.普通年能被4整除且不能被100整除的为闰年。如2004年就是闰年,1900年不是闰年
* 2.世纪年能被400整除的是闰年。如2000年是闰年，1900年不是闰年
*/
function leapYear(year) {
  return !(year % (year % 100 ? 4 : 400));
}
```

###### 二、参考答案

```js
function elapseSeconds() {
  var now = new Date();
  var then = new Date(
    now.getFullYear(),
    now.getMonth(),
    now.getDate(),
    0, 0, 0);
  var diff = now.getTime() - then.getTime();
  return Math.floor(diff/1000)
}
```