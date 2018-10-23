## 简答题

###### 一、参考答案
- {}
- new Object
- new Function
- Object.create()

###### 二、参考答案
- `Object.create(null)`
- `var dict = Object.setPrototypeOf({}, null);`

###### 三、参考答案
- 使用 hasOwnProperty 判断对象没有该属性
- Object.keys(obj).forEach(key)

###### 四、参考答案
有效。规范规定，数值后面的 `.` 是小数点，所以该语句相当是把 `1.`这个浮点数转换成字符串

###### 五、参考答案
这是原型的基本知识，略。

###### 六、参考答案
输出 `'10'` 和 `undefined`。原始类型不能添加属性。


###### 七、参考答案
输出 `undefined`。`new` 之后返回的值，如果没有 return，默认是返回实例。如果有 return，就是 return 后面的值。所以题中的 `a` 是数组 `[1, 2, 3]`，它没有 x 属性。


## 编程题

###### 一、参考答案

```js
function Animal(name) {
  this.name = name;
}

Animal.prototype.say = function (words) {
  console.log(this.name + ' say ' + words);
}

function Cat(name) {
  this.name = name;
}

Cat.prototype = Object.create(new Animal());

let cat = new Cat('kitty');

cat.say('hi')
```

###### 二、参考答案

请参考 <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create#Polyfill>