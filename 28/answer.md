## 简答题

###### 一、参考答案
```js
function* genFunc() { }
let genObj = genFunc();

const genFunc = function* () { };
let genObj = genFunc();

let obj = {
  * generatorMethod() {

  }
};
let genObj = obj.generatorMethod();

class MyClass {
  * generatorMethod() {

  }
}
let myInst = new MyClass();
let genObj = myInst.generatorMethod();
```

###### 二、参考答案：使用 `yield*`
```js
function* foo() {
  yield 'a';
  yield 'b';
}
function* bar() {
  yield 'x';
  yield* foo();
  yield 'y';
}
```

###### 三、参考答案：第一种写法，在返回时会迭代数组，也就是最终返回的是数组元素。第二种写法返回的是整个数组。

## 编程题

###### 一、参考答案

```js
const promiseTimers = [];
const lightsMap = {
  '1': '红',
  '2': '绿',
  '3': '黄'
}
for (let i = 1; i <= 3; i++) {
  promiseTimers.push(
    function () {
      return new Promise((resolve => {
        setTimeout(function () {
          console.log(lightsMap[i]);
          resolve();
        }, i * 1000);
      }))
    }
  );
}

function* execTimers() {
  while (true) {
    yield promiseTimers[0]();
    promiseTimers.push(promiseTimers.shift());
  }
}

let lights = execTimers();

function start() {
  let result = lights.next();
  if (!result.done) {
    result.value.then(() => run());
  }
}

start();
```