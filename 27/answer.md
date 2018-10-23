## 简答题

###### 一、参考答案
```js
const obj = {
  a: 1,
  b: 2
}
// 第一种遍历方法：`for...in`

for(let p in obj) {
  if (obj.hasOwnProperty(p)) {
    // do sth.
  }
}
// 第二种遍历方法：`Object.keys`

Object.keys(obj).forEach(key => {
  // do sth.
})
```

###### 二、参考答案
1. 首先，普通对象没有 `Symbol.iterator` 属性，导致了它不能被遍历。
2. 普通对象的键，是无序的，遍历不是用来处理这种数据结构的。遍历主要是指遍历集合，即 Array、Map等。这也是在提示用户，如果有遍历的需求，应该使用其他可遍历的数据结构，而不是普通的 Object。

参考：<http://2ality.com/2012/06/for-of-ff13.html>

###### 三、参考答案

`for...of` 可以与 `break`、`continue` 和 `return` 配合使用。
w
```js
const arr = [1, 2, 3];
for (let item of arr) {
  if (item === 2) {
    break;
  } else {
    console.log(item);
  }
}
```

## 编程题

###### 一、参考答案
```js
function take(iterable, start, end) {
  const iter = iterable[Symbol.iterator]();
  let idx = 0;
  let result = null;
  return {
    [Symbol.iterator]() {
      return this;
    },
    next() {
      while (idx < start) {
        iter.next();
        idx++;
      }
      if (idx > end) {
        result = { done: true };
      } else {
        result = iter.next();
      }
      idx++;
      return result;
    }
  };
}

const arr = [1, 2, 3, 4, 5, 6, 7, 8];
for (const x of take(arr, 3, 5)) {
  console.log(x);
}
```