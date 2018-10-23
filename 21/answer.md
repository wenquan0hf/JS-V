## 简答题

###### 一、参考答案
因为箭头函数没有构造函数 constructor

###### 二、参考答案
```js
let person = Person.call(new Person(), ('John'));
```

###### 三、参考答案
```js
var counter = (function() {
  var privateCounter = 0;
  function changeBy(val) {
    privateCounter += val;
  }
  return {
    increment: function() {
      changeBy(1);
    },
    decrement: function() {
      changeBy(-1);
    },
    value: function() {
      return privateCounter;
    }
  };
})();
```

###### 四、参考答案
通过 arguments.length 属性，根据参数个数不同做不同的事情。

###### 五、参考答案
- 函数节流（Throttling）：延迟函数执行。它会减少在某个时间段内函数执行的次数。
- 函数防抖（Debouncing）：限制函数在某个时间段内只执行一次。

比如缩放页面会一直触发 `window.resize` 的处理程序，此时就可以有规律地隔一段时间再执行一次处理程序，这就叫 函数节流。如果只在页面缩放完再执行处理程序，这就叫函数防抖，它只会在最后执行一次。


## 编程题

###### 一、参考答案

```js
function walk(obj, paths) {
  Object.keys(obj).forEach(key => {
    let value = obj[key];
    if (typeof value === 'object') {
      if (paths.find(path => path.id === value.id)) {
        let pathNames = paths.map(item => item.name);
        pathNames.push(key);
        let message = `${pathNames.join(' -> ')} 存在循环引用, 引用的对象的 id 是 ${value.id}`;
        throw new Error(message);
      } else {
        let prevLength = paths.length;
        paths.push(value);
        walk(value, paths);
        paths.length = prevLength;
      }
    }
  });
}

walk(tree, [tree]);
```
