## 简答题

###### 一、下述代码 `alert` 的结果是什么，请说明原因。

```js
let obj = {a: 1};
alert(obj);
```

###### 二、`除了 null 外，所有对象都有原型属性`，这句话是否正确，请说明原因。

###### 三、`对象的属性一定是字符串`，这句话是否正确，请说明原因。

###### 四、使用 `const` 声明的对象是否可以修改，请说明原因。

```js
const user = {
  name: "John"
};
// 会不会报错？
user.name = "Pete";
```


## 编程题

###### 一、请编写函数 `isObject`，判断输入的参数是否为对象。

###### 二、请编写函数 `isEmptyObject`，判断输入的参数是一个空对象。

###### 三、请编写函数 `getObjectKeys`，返回输入参数对象的所有键组成的数组，请至少提供两种解决方案。

###### 四、请编写函数，将输入的参数对象，如果某个属性值为数值，则将这个数值乘以 2，否则不做更改。

###### 五、假设某个浏览器不支持 `Object.assign` 方法，请给这个浏览器编写一个方法，完成类似的功能。
