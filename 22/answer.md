## 简答题

###### 一、参考答案
```js
// getter 是一个函数，在访问相应的属性时会触发
var obj = {
  log: ['a', 'b', 'c'],
  get latest() {
    if (this.log.length == 0) {
      return undefined;
    }
    return this.log[this.log.length - 1];
  }
}

console.log(obj.latest);

// setter 是一个函数，在设置相应的属性时会触发
var language = {
  set current(name) {
    this.log.push(name);
  },
  log: []
}

language.current = 'EN';
language.current = 'FA';

console.log(language.log);
// expected output: Array ["EN", "FA"]
```

## 编程题

###### 一、参考答案

```js
// 此题的目的，主要是温故一下面向对象的思考方式，可以使用原型继承。
// 在学生作业中，需要鼓励学生再给这些类添加一些方法和属性，比如毛色、脚的数量、年龄等等，使它们更加丰富

class Animal {
  constructor(name) {
    this.name = name;
  }

  sleep() {
    console.log(this.name + ' sleep ');
  }
}

class Cat extends Animal {
  constructor(name) {
    super(name);
  }

  miaow() {
    console.log(this.name + ' miaow ');
  }
}

class Dog extends Animal {
  constructor(name) {
    super(name);
  }

  bark() {
    console.log(this.name + ' bark ');
  }
}

let cat = new Cat('kitty');
// 从 Animal 继承而来的方法
cat.sleep();
// 自己特有的方法
cat.miaow();

let dog = new Dog('wangcai');
// 从 Animal 继承而来的方法
dog.sleep();
// 自己特有的方法
dog.bark();
```