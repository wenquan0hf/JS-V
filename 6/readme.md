## 简答题

###### 一、调用下面的 `func` 函数，它的返回值是什么，请说明原因。

```js
function func() {
  alert('hello world');
}
```

###### 二、下面的代码输出结果是什么，请说明原因。

```js
function func()
{
  return
  {
    name: 'john'
  };
}
func();
```

###### 三、下面的代码输出结果是什么，请说明原因。

```js
var Employee = {
  company: 'xyz'
}
var emp1 = Object.create(Employee);
delete emp1.company
console.log(emp1.company);
```
###### 四、函数的内部特殊对象 `arguments`，它都有哪些属性和方法，分别表示什么意思？

###### 五、调用自身的函数称之为递归函数，请问：函数可以调用到自身共有哪几种方式？

###### 六、请举例说明 `Object.create` 方法的第二个参数的用法。


## 编程题

###### 一、如果一个字符串从左往右和从右往左的结果是一样的，则称它为回文。请编写函数，判断一个字符串是否是回文。

###### 二、请编写函数 `multiple`，输出预期的结果：

```js
function multiple(){

}
console.log(multiple(1)(2)(3));// 1、2、3 三者相乘，结果输出 6
console.log(multiple(3)(4)(5));// 3、4、5 三者相乘，结果输出 60
```

###### 三、请将一个整数转换为千分位的字符串表示法，比如 `12345`，结果是 `12,345`

