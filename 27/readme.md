## 简答题

###### 一、遍历普通对象可以用什么方法？请举例说明。

###### 二、为什么默认情况下不能使用`for...of`遍历普通对象？请说明原因。

###### 三、使用`for...of`遍历数组和使用`forEach`遍历数组，有什么区别？请举例说明。


## 编程题

###### 一、请编写函数 `take(arr, startIndex, endIndex)`，使得在遍历该数组时，只能遍历出 `startIndex` 和 `endIndex` 之间的元素。比如：

```js
const arr = [1, 2, 3, 4, 5, 6, 7, 8];
for (const x of take(arr, 3, 5)) {
  console.log(x);
}
// 输出:
// 4
// 5
// 6
```
