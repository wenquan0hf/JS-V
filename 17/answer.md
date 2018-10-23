## 简答题

###### 一、参考答案
查看表 (View) 是在关系数据库中，将一组查询指令构成的结果集，组合成可查询的数据表的一种数据库对象。与数据表不同的是，数据表是一种实体结构(Physical Structure)，但查看表是一种虚拟结构(Virtual Structure)，在实体数据表中的改变都可以立刻反映在查看表中，不过部分数据库管理系统也支持具更新能力的查看表(Updatable View)。

查看表具有下列的好处：

- 可以将实体数据表隐藏起来，让外部程序的设计师无法得知实际的数据结构，降低数据库被攻击的风险。
- 在多数的情况下，查看表是只读的，外部程序无法直接透过查看表修改数据(具更新能力的查看表除外)。
- 简化查询，数据库管理员可以将高度复杂的查询，包装在查看表中，外部程序只需要直接访问该查看表即可取出需要的数据。

参考链接 <https://zh.wikipedia.org/wiki/%E8%A7%86%E5%9B%BE>

`TypeArray 视图(View)` 用来读写简单类型的二进制数据。

###### 二、参考答案

计算机里的数是用二进制表示的，最左边的这一位一般用来表示这个数是正数还是负数，这样的话这个数就是有符号整数。如果最左边这一位不用来表示正负，而是和后面的连在一起表示整数，那么就不能区分这个数是正还是负，就只能是正数，这就是无符号整数。

参考链接 <https://baike.baidu.com/item/%E6%97%A0%E7%AC%A6%E5%8F%B7%E6%95%B4%E6%95%B0>

###### 三、参考答案

`TypedArray 数组` 拥有普遍数组的方法和属性，但没有 `concat` 方法，其他的区别：

- TypedArray 数组的所有成员，都是同一种类型。
- TypedArray 数组的成员是连续的，不会有空位。
- TypedArray 数组成员的默认值为 0。比如，new Array(10)返回一个普通数组，里面没有任何成员，只是 10 个空位；new Uint8Array(10)返回一个 TypedArray 数组，里面 10 个成员都是 0。

参考链接 <http://es6.ruanyifeng.com/#docs/arraybuffer#TypedArray-%E8%A7%86%E5%9B%BE>

## 编程题

###### 一、参考答案
```html
<canvas id="canvas"></canvas>
```
```js
var canvas = document.getElementById('canvas');
var canvasWidth = canvas.width;
var canvasHeight = canvas.height;
var ctx = canvas.getContext('2d');
var canvasData = ctx.getImageData(0, 0, canvasWidth, canvasHeight);

function drawPixel (x, y, r, g, b, a) {
  var index = (x + y * canvasWidth) * 4;
  canvasData.data[index + 0] = r;
  canvasData.data[index + 1] = g;
  canvasData.data[index + 2] = b;
  canvasData.data[index + 3] = a;
}

for (var i = 0; i < 100; i++) {
  drawPixel(1, i, 255, 0, 0, 255);
  drawPixel(2, i, 255, 0, 0, 255);
}

ctx.putImageData(canvasData, 0, 0);
```