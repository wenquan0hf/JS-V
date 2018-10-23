## 简答题

###### 一、请简述 JSON 和 普遍 JavaScript 对象的区别。

###### 二、JSON 在实际工作中都有哪些典型的使用场景？

###### 三、合法的 JSON 都有哪些值？

###### 四、JSON 相对于 XML，都有什么优点和缺点？

###### 五、在使用 `JSON.stringify` 方法序列化 JavaScript 时，如果属性值是 `Date` 类型，默认是如何处理的？



## 编程题

###### 一、请编写函数 `cloneJSON`，用来复制一个 JSON 对象。

###### 二、请编写函数，用来打印 JSON 中所有的路径，比如下面的 JSON 对象：

```json
{
  "name": "John",
  "age": 23,
  "hobbies": ["reading books", "listening music"],
  "family": {
    "brother": {
      "name": "Jim",
      "age": 20,
      "hobbies": ["play games"]
    },
    "sister": {
      "name": "Kelly",
      "age": 18,
      "hobbies": ["dancing"]
    }
  }
}
```

它的所有路径为：

- `name`
- `age`
- `hobbies` (值为数组就停止不往下遍历)
- `family -> brother -> name`
- `family -> brother -> age`
- `family -> brother -> hobbies`
- `family -> sister -> name`
- `family -> sister -> age`
- `family -> sister -> hobbies`
