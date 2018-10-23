## 简答题

###### 一、使用 Proxy 会带来什么问题？

###### 二、什么时候`Reflect.deleteProperty`会返回 `false`？请举例说明。

###### 三、下述代码有什么问题，该如何修改？
```js
const person = {
  get name() {
    return this.name;
  },
  set name(name) {
    this.name = name;
  }
};
person.name = 'john';
console.log(person.name);
```


## 编程题

###### 一、如果将一个对象的属性值声明为数值，之后不想让它更改为其他类型的值，请问该如何实现？请编写实现代码。

###### 二、如何在不更改函数内部实现代码的前提下，测试这个函数的性能（也就是执行这个函数所花的时间）？请编写实现代码。

###### 三、假设下面的对象，我们规定以下划线开头的属性`_private`是私有属性，外部不能直接访问，但可以被自己的方法`method`访问，请编写实现代码。
```js
const myObj = {
  _private: 'private',
  public: 'public',
  method: function () {
    console.log(this._private);
  }
}
```