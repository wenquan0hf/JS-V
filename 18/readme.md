## 简答题

###### 一、请简述运算符 `==` 和 `===` 的区别。

###### 二、你知道如何复制 DOM 元素吗？有什么需要注意的地方？

###### 三、在一些老版本的 IE 浏览器中，`typeof` 会返回一些不标准的值，你知道都可能有哪些值吗？

###### 四、补充 todo 部分的代码，使得输出成立。

```js
function Cat() {}
// todo
const cat = new Cat();
console.log(Object.prototype.toString.call(cat)); // 预期输出为 '[object Cat]'
```

## 编程题

###### 一、编写函数 `isContainingSameIntegers(arr1, arr2)`，判断两个整数数组是否包含了相同的整数，比如 `[1, 2, 3]` 和 `[3, 2, 1]`，它俩包含了相同的整数。

###### 二、编写函数 `convertToType(value, type)`，可以将一种基本类型的值转换为另一种基本类型的值。

###### 三、编写函数 `changeObjectKey(obj, oldKey, newKey)`，用来更改对象的键名。

###### 四、编写函数 `cloneFunction(func)`，用来复制函数。

###### 五、编写函数 `cloneRegExp(regExp)`，用来复制正则。

###### 六、编写模板字符串的 tag 函数 `repeat(times)`，用来重复输出字符串，重复的次数是输入参数指定的值，比如：

```js
repeat(3)`abc`; // 输出为：'abcabcabc'
```
