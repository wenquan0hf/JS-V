## 简答题

###### 一、参考答案
字符串对象 是对象类型，有属性和方法。基本字符串是原始类型。

###### 二、参考答案
可以使用单引号、双引号以及模板字符串。

###### 三、参考答案
left 和 right 的话，会有歧义，因为有些语言就是从右到左书写的。

###### 四、参考答案
1. `substr(from, length)`，第二个参数指定长度
2. `substring(from, to)`，第二个参数指定索引
3. `slice(from, to)` 和 `substring(from, to)`:
  1. 共同点:
    1. 如果 `from` 和 `to` 相等，返回空字符串。
    2. 如果没有 `to`，则截取到字符串末尾。
    3. 参数大于字符串长度时，则使用字符串长度替代。
  2. `substring` 的特殊：
    1. 如果 `to` 大于 `from`，则交换两个参数。
    2. 如果参数是负数或者 NaN，则使用 0 替代。
  3. `slice` 的特殊：
    1. 如果 `to` 大于 `from`，不会交换两个参数。
    2. 如果 `from` 是负数，则相当于设置为字符串的末尾。
    2. 如果 `to` 是负数，则相当于设置为 `string.length – Math.abs(stop)`，如果值为 0，则使用 `Math.max(0, string.length + stop)`。

参考链接 <https://stackoverflow.com/questions/2243824/what-is-the-difference-between-string-slice-and-string-substring>

###### 五、参考答案
两者都是查找字符串的方法，但 `indexOf` 的参数是普通字符串，`search` 方法的参数是正则表达式。

###### 六、参考答案
按照 ascii 码。

###### 七、参考答案
1. str[index]
1. str.charAt(index)

###### 八、参考答案

- concat

###### 九、参考答案

针对 null/undefined/symbols，String() 方法会有特殊的处理


## 编程题

###### 一、参考答案
```js
function isString (str) {
  return typeof str === 'string';
}
// OR
function isString (str) {
  return str instanceof String;
}
// OR
function isString (str) {
  return Object.prototype.toString.call(str) === '[object String]';
}
```

###### 二、参考答案
```js
// 循环法
function find(str, char) {
  for(var i = 0; i < str.length; i++) {
    if (str[i] === char) {
      return i;
    }
  }
}
// indexOf
function find(str, char) {
  return str.indexOf(char);
}
```

###### 三、参考答案
```js
// 按照ascii码值提取法
function filterStr(str) {
  var result = '';
  for(var i = 0; i < str.length; i++) {
    var charCode = str[i].charCodeAt(0);
    // 大写字母的ascii码范围是 65 到 90，小写字母的ascii范围是97到122
    if (charCode >= 65 &&  charCode <= 90 || charCode >= 97 && charCode <= 122) {
      result += str[i];
    }
  }
  return result;
}
// 正则法
function filterStr(str) {
  return str.replace(/[^a-z]/gi, '');
}
```
###### 四、参考答案
```js
function replaceStr(str, repeatTimes, word, replaceWord) {
  var words = str.split(' ');
  var times = 1;
  for(var i = 0; i < words.length; i++) {
    if (words[i] === word) {
      if (times === repeatTimes) {
        words[i] = replaceWord;
        break;
      } else {
        times++;
      }
    }
  }
  return words.join(' ');
}
```
