## 简答题
###### 一、参考答案

输出 `[object Object]`，因为 alert 方法会将参数先转换成字符串。

###### 二、参考答案

不对。因为可以创建没有原型的对象，比如 `Object.create(null)`

###### 三、参考答案

不对。普通对象的属性还可以是 `symbol`，Map 对象还可以是 DOM 元素。

###### 四、参考答案

可以修改。根据规范，使用 const 声明的变量，不能重新定义或者赋值，但如果是对象的话，是可以修改它的属性的。

## 编程题

###### 一、参考答案
```js
function isObject(obj) {
  return obj === Object(obj);
}
// OR
function isObject(obj) {
  return Object.prototype.toString.call(obj) === '[object Object]';
}
```

###### 二、参考答案
```js
function isEmptyObject(obj) {
  for(var prop in obj) {
    if(obj.hasOwnProperty(prop)) {
      return false;
    }
  }
  return JSON.stringify(obj) === JSON.stringify({});
}
// OR
function isEmptyObject(obj) {
  return Object.keys(obj).length === 0 && obj.constructor === Object;
}
```

###### 三、参考答案
```js
function getObjectKeys(obj) {
  var keys = [];
  for(var prop in obj) {
    if(obj.hasOwnProperty(prop)) {
      keys.push(prop);
    }
  }
  return keys;
}
// OR
function getObjectKeys(obj) {
  return Object.keys(obj);
}
```

###### 四、参考答案
```js
function func(obj) {
  for(var prop in obj) {
    if(obj.hasOwnProperty(prop) && typeof(obj[prop]) === 'number') {
      obj[prop] = obj[prop] * 2;
    }
  }
}
```

###### 五、参考答案
```js
if (typeof Object.assign != 'function') {
  // Must be writable: true, enumerable: false, configurable: true
  Object.defineProperty(Object, "assign", {
    value: function assign(target, varArgs) { // .length of function is 2
      'use strict';
      if (target == null) { // TypeError if undefined or null
        throw new TypeError('Cannot convert undefined or null to object');
      }

      var to = Object(target);

      for (var index = 1; index < arguments.length; index++) {
        var nextSource = arguments[index];

        if (nextSource != null) { // Skip over if undefined or null
          for (var nextKey in nextSource) {
            // Avoid bugs when hasOwnProperty is shadowed
            if (Object.prototype.hasOwnProperty.call(nextSource, nextKey)) {
              to[nextKey] = nextSource[nextKey];
            }
          }
        }
      }
      return to;
    },
    writable: true,
    configurable: true
  });
}
```

参考链接 <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign>