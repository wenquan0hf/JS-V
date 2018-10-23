## 简答题

###### 一、参考答案
- JSON 的键值必须使用双引号。
- JSON 中不能写注释。
- JSON 最后一项之后不能有多余的逗号。
- JSON 的值有一些要求，比如数值类型只能使用十进制，不能是函数、正则、日期等等，只能是下面的值：
  * string
  * number
  * object
  * array
  * true
  * false
  * null

###### 二、参考答案
- 前后端数据通信格式
- 配置文件

###### 三、参考答案
JSON 可以是4种原始类型 (strings, numbers, booleans, and null) 和两种结构化类型(objects and arrays)。

###### 四、参考答案

相同点
- 都能"自我说明" (人类可读)
- 都是层级化的(值里面可以再有值)
- 都可以被很多语言解析
- 都可以在 XMLHttpRequest 中使用

不同点
- JSON 不使用结束标签
- JSON 比较简短
- JSON 读写更快
- JSON 可以使用数组

还有一个很重要的区别是，xml需要使用专门的xml解析器，而JSON可以被标准的JavaScript函数解析。

JSON 比 XML 更容易解析，对 JavaScript 更加友好。

参考链接 <https://www.w3schools.com/js/js_json_xml.asp>

###### 五、参考答案
调用 `date.toJSON()` 方法。

## 编程题

###### 一、参考答案

```js
function clone(obj) {
  return JSON.parse(JSON.stringify(obj));
}
// 如果是浅拷贝，也可以使用 Object.assign 等方法
```

###### 二、参考答案

```js
function printJsonPaths(json) {
  var paths = [];

  function walk(json, tempPaths) {
    Object.keys(json).forEach(key => {
      var preLength = tempPaths.length;
      tempPaths.push(key);
      if (typeof(json[key]) === 'object' && !Array.isArray(json[key])) {
        walk(json[key], tempPaths);
      } else {
        paths.push(tempPaths.join(' -> '));
      }
      tempPaths.length = preLength;
    });
  }

  Object.keys(json).forEach(key => {
    if (typeof(json[key]) === 'object' && !Array.isArray(json[key])) {
      walk(json[key], [key]);
    } else {
      paths.push(key);
    }
  });

  console.log(paths)
}
```