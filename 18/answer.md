## 简答题

###### 一、参考答案
`==` 会有隐式类型转换的问题。比如 `2 == '2'` 为 `true`，但 `2 === '2'` 为 `false`。

###### 二、参考答案
可以使用 `Node.cloneNode()` 方法。

克隆一个元素节点会拷贝它所有的属性以及属性值,当然也就包括了属性上绑定的事件(比如onclick="alert(1)"),但不会拷贝那些使用addEventListener()方法或者node.onclick = fn这种用JavaScript动态绑定的事件.

参考链接 <https://developer.mozilla.org/zh-CN/docs/Web/API/Node/cloneNode>

###### 三、参考答案
这个是 JScript 的问题，比如在IE7，在访问一些 COM 组件对象的属性时，如果该对象没有这个属性，则会返回 `unknown`，还有可能会返回 `date`。

这个问题可以参考 《JavaScript语言精髓和编程实践》的 388页 `1.7.1. 宿主环境下的特殊类型系统`。该电子书网上可以下载。

###### 四、参考答案
```js
Object.defineProperty(Cat.prototype, Symbol.toStringTag, {
  value: 'Cat'
});
```

## 编程题

###### 一、参考答案
```js
function isContainingSameIntegers(arr1, arr2) {
  return JSON.stringify(arr1.sort()) === JSON.stringify(arr2.sort());
}
```

###### 二、参考答案
```js
// 有这样的意识就行，具体怎么写不做要求，因为还要看实际使用场景的
function convertToType(value, type) {
  switch (type) {
    case 'string':
      return String(value);
    case 'number':
      return Number(value);
    case 'boolean':
      return Boolean(value);
  }
}
```

###### 三、参考答案
```js
function changeObjectKey(obj, oldKey, newKey) {
  if (obj.hasOwnProperty(oldKey)) {
    obj[newKey] = obj[oldKey];
    delete obj[oldKey];
  }
}
```

###### 四、参考答案
```js
function cloneFunction(func) {
  return func.bind();
}
```

参考链接 <https://stackoverflow.com/questions/1833588/javascript-clone-a-function>

###### 五、参考答案
```js
function cloneRegExp(regexp) {
  const flagMap = {
    global: 'g',
    ignoreCase: 'i',
    multiline: 'm',
    dotAll: 's',
    sticky: 'y',
    unicode: 'u'
  };

  const flags = Object.keys(flagMap).map(flag => (
    regexp[flag] ? flagMap[flag] : ''
  )).join('');

  const clonedRegexp = new RegExp(regexp.source, flags);

  clonedRegexp.lastIndex = regexp.lastIndex

  return clonedRegexp;
}
```

###### 六、参考答案
```js
/**
 * Tag function that returns a string that conforms
 * to the normal (“cooked”) interpretation of
 * template literals.
 * `String.raw` is similar, but follows the “raw”
 * interpretation.
 */
function cook(strs, ...substs) {
  return substs.reduce(
    (prev,cur,i) => prev+cur+strs[i+1],
    strs[0]
  );
}

function repeat(times) {
  return function (...args) {
    return cook(...args).repeat(times);
  };
}
```