## 简答题
###### 一、略

###### 二、略

###### 三、略

###### 四、略

###### 五、参考答案
1. `未声明` 是指未使用 `var`、`let`或者`const` 声明变量。
2. `未定义` 是指使用 `var`或者`let`声明了变量，但没有赋值。

###### 六、参考答案
`typeof` 能方便地检测基本类型，适合检测变量是否定义，但无法检测对象的具体类型。

```js
let arr = [];
console.log(typeof arr); // 'object'
```

## 编程题

###### 一、参考答案
```js
const str = 'dcab';

function sortString(str) {
  var arr = str.split('');
  var tmp;
  for (var i = 0; i < arr.length; i++) {
    for (var j = i + 1; j < arr.length; j++) {
      if (arr[i].charCodeAt(0) > arr[j].charCodeAt(0)) {
        tmp = arr[i];
        arr[i] = arr[j];
        arr[j] = tmp;
      }
    }
  }
  return arr.join('');
}

console.log(sortString(str))
```

###### 二、参考答案
```js
const a = 100;
let aStr = a.toString(2);

while (aStr.length < 8) {
  aStr = '0' + aStr;
}
```