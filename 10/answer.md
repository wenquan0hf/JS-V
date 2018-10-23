## 简答题
###### 一、参考答案

1. `arr = [];`
2. `arr.length = 0;`
3. `arr.splice(0, arr.length);`
4. ```js
while(arr.length > 0) {
  arr.pop();
}
```

###### 二、参考答案
1. loop
2. slice
3. Array.from()
4. concat
5. 扩展运行符 `...`

###### 三、参考答案
输出 arr 的值，this 指向的是 arr。

###### 四、参考答案
```js
var points = [
  [1, 2],
  [3, 4],
  [5, 6]
];
```
上述二维数组可用来表示坐标上面的点，其中 `[1, 2]` 表示横坐标是 `1`，纵坐标是 `2`。

## 编程题

###### 一、参考答案

```js
function isArray(arg) {
  return Object.prototype.toString.call(arg) === '[object Array]';
};
// 或者直接使用 Array.isArray
```


###### 二、参考答案

```js
function findMaxAndMin(arr) {
  var max = arr[0];
  var min = arr[0];
  for(var i = 0; i < arr.length; i++) {
    if (min > arr[i]) {
      min = arr[i];
    }
    if (max < arr[i]) {
      max = arr[i];
    }
  }
  console.log(max);
  console.log(min);
}
// 或者使用 Math.max 和 Math.min 也可以
function findMaxAndMin(arr) {
  var max = Math.max.apply(null, arr);
  var min = Math.min.apply(null, arr);
  console.log(max);
  console.log(min);
}
```

###### 三、参考答案

```js
// 方法比较多，这里仅演示map法
function unique(arr) {
  var map = {};
  return arr.filter(function (item) {
    if (map[item]) {
      return false;
    }
    map[item] = true;
    return true;
  });
}
```

###### 四、参考答案

```js
// 双重循环暴力解法
function twoSum(nums, target) {
  for (var i = 0, l = nums.length; i < l; i++) {
    for(var j = i + 1; j < l; j++) {
      if (nums[i] + nums[j] === target) {
        return [i, j];
      }
    }
  }
}
// 利用map的性能更好的解法
function twoSum(nums, target) {
  var hash = {};
  for(var i = 0; i < nums.length; i++) {
    var num = nums[i];
    if(hash[num] !== undefined) {
      return [hash[num], i];
    } else {
      hash[target - num] = i;
    }
  }
  return [];
}
```