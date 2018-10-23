## 简答题

###### 一、创建日期对象 `new Date`，它的参数有几种类型？

###### 二、`getYear` 和 `getFullYear` 有什么区别？

###### 三、下面哪个方法性能更高？请编写代码证明你的猜想。

```js
function diff1(date1, date2) {
  return date2 - date1;
}

function diff2(date1, date2) {
  return date2.getTime() - date1.getTime();
}
```

## 编程题

###### 一、请编写函数 `isLeapYear`，判断输入的年份是否为闰年。

###### 二、请编写函数计算当天的此时此刻已经过去了多少秒。