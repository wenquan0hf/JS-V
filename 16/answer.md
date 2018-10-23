## 简答题

###### 一、参考答案
ArrayBuffer 对象、TypedArray 视图和 DataView 视图是 JavaScript 操作二进制数据的一个接口。
- ArrayBuffer对象：代表内存之中的一段二进制数据，可以通过“视图”进行操作。“视图”部署了数组接口，这意味着，可以用数组的方法操作内存。
- TypedArray视图：共包括 9 种类型的视图，比如Uint8Array（无符号 8 位整数）数组视图, Int16Array（16 位整数）数组视图, Float32Array（32 位浮点数）数组视图等等。
- DataView视图：可以自定义复合格式的视图，比如第一个字节是 Uint8（无符号 8 位整数）、第二、三个字节是 Int16（16 位整数）、第四个字节开始是 Float32（32 位浮点数）等等，此外还可以自定义字节序。

简单说，ArrayBuffer对象代表原始的二进制数据，TypedArray 视图用来读写简单类型的二进制数据，DataView视图用来读写复杂类型的二进制数据。

参考链接 <http://es6.ruanyifeng.com/#docs/arraybuffer>

###### 二、参考答案
- File API
- XMLHttpRequest
- Fetch API
- Canvas
- WebSockets

###### 三、参考答案
输出 `-1`。

`Int8Array` 是 8 位有符号整数，0xff，二进制是 `11111111`，第一位的 `1` 是符号位，表示 `负`，结果为 `-128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = -1`。


###### 四、参考答案
输出 `255`。

`Uint8Array` 是 8 位无符号整数，0xff，二进制是 `11111111`，结果为 `128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255`。


## 编程题

###### 一、参考答案

```js
let tarr = new Uint8Array([0,1,2]);
Array.prototype.slice.call(tarr);

// OR
[...tarr]

// OR
Array.from(tarr)
```

###### 二、参考答案

```js
var toString = Object.prototype.toString
var names = {
    '[object Int8Array]': true
  , '[object Int16Array]': true
  , '[object Int32Array]': true
  , '[object Uint8Array]': true
  , '[object Uint8ClampedArray]': true
  , '[object Uint16Array]': true
  , '[object Uint32Array]': true
  , '[object Float32Array]': true
  , '[object Float64Array]': true
}

function isTypedArray(arr) {
  return (
       isStrictTypedArray(arr)
    || isLooseTypedArray(arr)
  )
}

function isStrictTypedArray(arr) {
  return (
       arr instanceof Int8Array
    || arr instanceof Int16Array
    || arr instanceof Int32Array
    || arr instanceof Uint8Array
    || arr instanceof Uint8ClampedArray
    || arr instanceof Uint16Array
    || arr instanceof Uint32Array
    || arr instanceof Float32Array
    || arr instanceof Float64Array
  )
}

function isLooseTypedArray(arr) {
  return names[toString.call(arr)]
}
```

参考代码 <https://github.com/hughsk/is-typedarray/blob/master/index.js>