## 简答题

###### 一、参考答案
```js
const a = 1;
const b = 2;
const c = a === 1 ? (b === 2 ? 3 : 4) : 5;
```

###### 二、参考答案
```js
12 ^ 15 的执行过程：

12 (base 10) = 00001100 (base 2)
15 (base 10) = 00001111 (base 2)
--------------------------------
12 ^ 15 (base 10) = 00000011 (base 2) = 3 (base 10)
```

###### 三、参考答案
第二段代码的 `i` 会自增两次，第一段代码的 `i` 只会自增一次。


###### 四、请简述下述运算符的作用并举例说明：

- `typeof`：检测变量类型
- `delete`：删除对象属性
- `void`：执行表达式，但无返回值
- `,`(逗号运算符)：执行两边表达式，返回最后的表达式的值
- `()`(分组运算符)：分组操作符，可以控制表达式的优先级
- `in`：检测对象是否拥有某个属性
- `instanceof`：检测某个对象是否为某个对象的类型。
- `new`：创建某个对象类型的实例
- `...`(扩展运算符)：扩展操作符允许一个表达式展开为多个值。

参考链接：<https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_Operators>

## 编程题

###### 一、参考答案
```js
let one = 1;
let two = 2;

// 方法一：使用中间变量
let temp = one;
one = two;
two = temp;

// 方法二：解构赋值
[one, two] = [two, one];

// 方法三：数学求和法
one = one + two;
two = one - two;
one = one - two;

console.log(one, two); // 输出 2, 1

```


###### 二、参考答案

```js
const seconds = 1000000;
const days = Math.floor(seconds / (60 * 60 * 24));
let leftSeconds = Math.floor(seconds % (60 * 60 * 24));
const hours = Math.floor(leftSeconds / (60 * 60));
leftSeconds = Math.floor(leftSeconds % (60 * 60));
const minutes = Math.floor(leftSeconds / 60);
leftSeconds = Math.floor(leftSeconds % 60);
console.log(days + '天' + hours + '时' + minutes + '分' + leftSeconds + '秒')
```