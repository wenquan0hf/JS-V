## 简答题
###### 一、参考答案
```js
// 下载图片是一个异步过程
var photo = downloadPhoto('http://coolcats.com/cat.gif');
// 紧接着访问 photo，并不能得到结果
console.log(photo);// undefined

// 异步一般需要用到回调
downloadPhoto('http://coolcats.com/cat.gif', function(photo){
  // 此时才能拿到图片数据
  console.log(photo);
});
```

###### 二、参考答案：<http://callbackhell.com/>

`call hell` 指的是多重回调嵌套后代码缩进显得比较夸张的现象。

```js
fs.readdir(source, function (err, files) {
  if (err) {
    console.log('Error finding files: ' + err)
  } else {
    files.forEach(function (filename, fileIndex) {
      console.log(filename)
      gm(source + filename).size(function (err, values) {
        if (err) {
          console.log('Error identifying file size: ' + err)
        } else {
          console.log(filename + ' : ' + values)
          aspect = (values.width / values.height)
          widths.forEach(function (width, widthIndex) {
            height = Math.round(width / aspect)
            console.log('resizing ' + filename + 'to ' + height + 'x' + height)
            this.resize(width, height).write(dest + 'w' + width + '_' + filename, function(err) {
              if (err) console.log('Error writing file: ' + err)
            })
          }.bind(this))
        }
      })
    })
  }
})
```

###### 三、参考答案：<https://zhuanlan.zhihu.com/p/33058983>

js引擎遇到一个异步事件后并不会一直等待其返回结果，而是会将这个事件挂起，继续执行执行栈中的其他任务。当一个异步事件返回结果后，js会将这个事件加入与当前执行栈不同的另一个队列，我们称之为事件队列。被放入事件队列不会立刻执行其回调，而是等待当前执行栈中的所有任务都执行完毕， 主线程处于闲置状态时，主线程会去查找事件队列是否有任务。如果有，那么主线程会从中取出排在第一位的事件，并把这个事件对应的回调放入执行栈中，然后执行其中的同步代码...，如此反复，这样就形成了一个无限的循环。这就是这个过程被称为“事件循环（Event Loop）”的原因。


## 编程题

###### 一、参考答案
```js
const promiseTimers = [];
for (let i = 0; i < 10; i++) {
  promiseTimers.push(
    new Promise((resolve => {
      setTimeout(function () {
        console.log(i);
        resolve();
      }, i * 1000);
    }))
  );
}

Promise.all(promiseTimers).then(values => {
  console.log('计时器全部执行完毕');
});
```