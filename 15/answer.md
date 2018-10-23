## 简答题

###### 一、参考答案

`length` 是用于有序的数据结构，比如 array；而 `size` 主要用于无序的集合，比如 `Map`、`Set`。

参考链接 <http://2ality.com/2015/01/es6-maps-sets.html>

## 编程题

###### 一、参考答案
```js
function uniq(a) {
  return Array.from(new Set(a));
}
```

###### 二、参考答案
```js
let a = new Set([1, 2, 3]);
let b = new Set([4, 3, 2]);
let intersection = new Set([...a].filter(x => b.has(x)));
```

###### 三、参考答案
```js
function func(arr) {
  var hash = {};
  var words = [];

  for(let item of arr) {
    let key = item.toLowerCase().split('').sort().join('');
    if (!hash[key]) {
      hash[key] = true;
      words.push(item);
    }
  }

  return words;
}
```