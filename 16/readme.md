## 简答题

###### 一、请简述 `ArrayBuffer`、`TypeArray` 和 `DataView` 的概念和联系。

###### 二、请例举一些 `TypeArray` 的使用场景。

###### 三、下面的代码输出结果是什么，请说明原因。

```js
let buffer = new ArrayBuffer(1024);
let a = new Int8Array(buffer);
a[0] = 0xff;
console.log(a[0]);
```

###### 四、下面的代码输出结果是什么，请说明原因。

```js
let buffer = new ArrayBuffer(1024);
let a = new Uint8Array(buffer);
a[0] = 0xff;
console.log(a[0]);
```


## 编程题

###### 一、编写程序，将 `TypeArray` 转换成普通数组，至少提供两种解决方案。

###### 二、编写函数 `isTypedArray`，判断输入的参数值是否为 `TypedArray`。
