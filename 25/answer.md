## 简答题
###### 一、参考答案
基本思想就是利用立即执行函数表达式，将一些信息封装在函数内部，最后返回的是一个对象。

问这道题也是想让学生了解一下模块化的历史知识，自己去网上找些文章看下就可以了，比如 <http://www.adequatelygood.com/JavaScript-Module-Pattern-In-Depth.html>

###### 二、参考答案

`tree shaking`，最初是 Rollup 工具提出来的：<https://github.com/rollup/rollup#tree-shaking>。

在引入一个包时，同时也会引入很多没有用到的代码，`tree shaking`就是将这些没有用到的代码剔除的技术。

###### 三、参考答案
当抛出单个值时，可以使用  `export default`

```js
// module "my-module.js"
export default function cube(x) {
  return x * x * x;
}
```
然后在其他文件中：
```js
import cube from 'my-module';
console.log(cube(3)); // 27
```

###### 四、参考答案

使用 Rollup 或者 webpack 都可以。略。


## 编程题

###### 一、参考答案
此题的目的主要是让学生知道有循环依赖这么一回事儿。

```js
// 模块 a
import { bar } from './b.js';

export function foo() {
  bar();
}
```

```js
// 模块 b
import { foo } from './a.js';

export function bar() {
  if (Math.random()) {
    foo();
  }
}
```

```html
// html 测试代码
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>循环依赖测试</title>
</head>
<body>
<script type="module" src="a.js"></script>
<script type="module" src="b.js"></script>
</body>
</html>
```