## 简答题

###### 一、箭头函数为什么不能使用 `new` 的方式来生成实例对象？

###### 二、课程中的思考题，下面的最后一行代码如何修改，使得函数 Person 中的 this 是 Person 的实例？
```js
function Person(name) {
  if (this instanceof Person) {
    this.name = name;
  } else {
    throw new Error('You must use new with Person');
  }
}

let person = Person('John');
```

###### 三、在 JavaScript 中，如何实现私有方法？

###### 四、在 JavaScript 中，如何实现函数重载？

###### 五、什么是函数节流和函数防抖？请举例说明。


## 编程题

###### 一、下面的对象 tree，最后一行代码，tree 的 subTree 属性引用了它自身，这种现象叫循环引用，此时使用 `JSON.stringify(tree)` 去序列化 `tree` 时，会报 `TypeError: Converting circular structure to JSON` 的错误。请编写程序，检测某个对象是否存在循环引用，如果存在循环引用，需要指出哪个属性存在循环引用，循环引用的是哪个对象。

```js
// 每个对象的 id 都是唯一的，也就是可以根据 id 找到相应的对象。
const objects = [
  { id: 1, name: 'a' },
  { id: 2, name: 'b' },
  { id: 3, name: 'c' },
  { id: 4, name: 'tree' }
];
// tree 是 objects 对象列表中的某个一对象。
const tree = objects.find(item => item.id === 4);
// 上面的 tree 对象还不存在循环引用，加上下面一句时也没有产生循环引用。
tree.subTree = objects.find(item => item.id === 1);
// 但如果是下面一句，就产生了循环引用。
tree.subTree = objects.find(item => item.id === 4);
// 如果是下面一句，也会产生循环引用。
tree.subTree = {
  name: 'subTree',
  children: objects.find(item => item.id === 4)
};

// todo：请在此处补充代码，可检测 tree 对象是否存在循环引用的情况
```

