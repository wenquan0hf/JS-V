## 简答题
###### 一、参考答案：会带来额外的性能开销。

尽管使用代理可以创造性地控制对象的访问，但是大量的控制操作将带来性能问题。可以在对性能要求不高的程序里使用代理，但是若多次执行代码时仍然要小心谨慎。

###### 二、参考答案：
```js
Reflect.deleteProperty(Object.freeze({foo: 1}), 'foo'); // false
```
###### 三、参考答案：
```js
const person = {
  get name() {
    return this._name;
  },
  set name(name) {
    this._name = name;
  }
};
person.name = 'john';
console.log(person.name);
```

## 编程题

###### 一、参考答案：使用 Proxy 的 set
```js
let validator = {
  set: function (obj, prop, value) {
    if (!Number.isInteger(value)) {
      throw new TypeError('The age is not an integer');
    }
    obj[prop] = value;
    return true;
  }
};

let person = new Proxy({}, validator);

person.age = 100;
console.log(person.age);
person.age = 'young';
```

###### 二、参考答案：使用 Proxy 的 apply
```js
function isPrime(number) {
  if (number < 2) {
    return false;
  }
  for (let i = 2; i < number; i++) {
    if (number % i === 0) {
      return false;
    }
  }
  return true;
}

isPrime = new Proxy(isPrime, {
  apply: (target, thisArg, args) => {
    console.time("isPrime");
    const result = target.apply(thisArg, args);
    console.timeEnd("isPrime");
    return result;
  }
});

console.log(isPrime(1299827))
```

###### 三、参考答案
```js
function privateProps(obj) {
  const handler = {
    get(obj, prop) {
      if (!prop.startsWith('_')) {
        let value = Reflect.get(obj, prop);
        if (typeof value === 'function') {
          value = value.bind(obj);
        }
        return value;
      }
    }
  };
  return new Proxy(obj, handler);
}

const myObj = {
  _private: 'private',
  public: 'public',
  method: function () {
    console.log(this._private);
  }
}
const myProxy = privateProps(myObj);

console.log(myProxy._private); // 输出 undefined，不能访问私有变量
console.log(myProxy.public); // 输出 public，可以访问公有变量
myProxy.method();  // 输出 private，自己的方法可以访问私有变量
```