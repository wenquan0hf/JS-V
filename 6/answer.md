## 简答题

###### 一、参考答案
返回 `undefined`，当函数没有显式的返回值时，函数返回值为 `undefined`。注意，`alert` 并不是返回值。

###### 二、参考答案
返回 `undefined`，`return` 后面没内容时，会自动插入分号结束语句，函数执行 return 语句所在行时就直接返回了。

###### 三、参考答案
输出`xyz`，原型上的属性无法删除。

###### 四、参考答案
1. `length` 属性：表示实参的数量。
2. `callee` 属性：指向`当前被调用的函数本身`。
3. `caller` 属性：指向调用`当前被调用函数`的函数，目前已废弃。

###### 五、参考答案
```js
// 1. 通过函数名调用自身
function func(){
  func();
}

// 2. 通过函数表达式的名称调用
var func = function(){
  func();
}

// 3. 通过 arguments.callee 调用自身
function func(){
  arguments.callee.call();
}
```

###### 六、参考答案
`Object.create()` 的第二个参数和 `Object.defineProperties()` 对应，在之后《原型》课程的第一节会有具体讲解。

参考链接：<https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/create>


## 编程题

###### 一、参考答案

```js
// 如果考虑了字符串大小写的问题，也算正确

// 方法一：for 循环
function palindrome(str) {
 var len = str.length;
 for (var i = 0; i < len/2; i++) {
   if (str[i] !== str[len - 1 - i]) {
       return false;
   }
 }
 return true;
}

// 方法一改进版本：while 循环
function palindrome(str) {
  var start = 0;
  var end = str.length - 1;
  while (start++ < end--) {
    if (str[start] !== str[end]) {
      return false;
    }
  }
  return true;
}

// 方法二：利用数组的 `reverse` 方法
function palindrome(str) {
  var reverseStr = str.split('').reverse().join('');
  return reverseStr === lowRegStr;
}
```

###### 二、参考答案

```js
function mul (x) {
  return function (y) {
    return function (z) {
      return x * y * z;
    };
  };
}
```

###### 三、参考答案

```js
// 方法一：while 循环
function func(num) {
  var str = num.toString();
  var result = '';
  var index = 0;
  var length = str.length - 1;
  while (length >= 0) {
    if (index % 3 === 0 && index !== 0) {
      result += ',' + str[length];
    } else {
      result += str[length];
    }
    length--;
    index++;
  }
  return result.split('').reverse().join('');
}

// 方法二：正则
function func(num) {
  return num.toString().replace(/(\d{1,3})(?=(\d{3})+$)/g,'$1,');
}
```

> 正则解释
1. \d     匹配数字相当于[0-9]
2. {m,n}  匹配的数目大于m小于n，所以\d{1,3}的意思就是匹配1到3个数字
3. ?=     正向前瞻。举个例子来说明：

>/\d/会匹配一个数字，`/\d(?=\w)/` 依然只匹配一个数字，但是要求数字后面还要跟一个字母，比如：
> '1a'.match(/\d(?=\w)/) 结果为 `1`

>所以 `/(\d{1,3})(?=(\d{3})+$)/g` 这个正则表达式的意思就是：

> 匹配 1 到 3 个数字，并且这个数字后面要跟着 3 的倍数的数字，也就是3,6,9,...个数字，所以：
> '123456789'.match(/(\d{1,3})(?=(\d{3})+$)/g) 会匹配到 ["123", "456"]