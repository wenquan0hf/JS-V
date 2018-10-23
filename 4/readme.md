## 简答题

###### 一、请编写一段能正常运行的三元条件运算符嵌套三元条件运算符的 JavaScript 语句块代码。

###### 二、请演示 `12 ^ 15` 的详细执行过程。

###### 三、请简述下面两段代码的不同之处。

```js
// 代码片段一
let arr = [1, 2, 3];
let i = 0;
arr[i++] += 5;

// 代码片段二
let arr = [1, 2, 3];
let i = 0;
arr[i++] = arr[i++] + 5;
```

###### 四、请简述下述运算符的作用并举例说明：

- `typeof`
- `delete`
- `void`
- `,`(逗号运算符)
- `()`(分组运算符)
- `in`
- `instanceof`
- `new`
- `...`(扩展运算符)


## 编程题

###### 一、编写程序，实现交换下述两个变量的值，至少需要提供 3 种解决方案：

```js
let one = 1;
let two = 2;
// todo: 请在这里补充代码
console.log(one, two); // 输出 2, 1
```

###### 二、给定一个以秒为单位的数值，输出`天...时...分...秒`的格式，比如，`1000000` 秒，输出结果为 `11天13时46分40秒`