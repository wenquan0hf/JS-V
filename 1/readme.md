## 简答题

###### 一、安装 Sublime Text、Chrome、Firefox

请在自己的电脑上安装 Sublime Text 编辑器、Chrome 浏览器、Firefox 浏览器。

###### 二、创建 `hello world` 文件

在实际工作中，调试代码的时候，一般不会使用视频课程中的 `document.write` 方法，最常用的方法是使用 `console.log` 方法。

- 首先，在 Sublime Text 中 输入下面的代码：

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>hello world</title>
</head>
<body>
<script src="hello_world.js"></script>
</body>
</html>
```

将文件保存为 `hello_world.html`。

- 然后，在 Sublime Text 中输入下面的代码：

```js
console.log('hello world');
```

将文件保存为 `hello_world.js`。

> 注意，`hello_world.html` 和 `hello_world.js` 这两个文件要放在同个目录中。

###### 三、在 Chrome 和 Firefox 中运行页面

- 在 Chrome 中打开 `hello_world.html`，然后分别找出两种打开控制台的方式，其中一种使用鼠标，另外一种使用快捷键，确认控制台输出了 `hello world`。

- 在 Firefox 中打开 `hello_world.html`，然后分别找出两种打开控制台的方式，其中一种使用鼠标，另外一种使用快捷键，确认控制台输出了 `hello world`。


###### 四、使用 Node.js 在命令行中执行 `hello_world.js`

[Node.js](https://nodejs.org/) 是目前前端工程师非常喜欢的开发语言，它的语法和 JavaScript 一样，也支持 `console.log` 方法。

- 按照上面的官网地址，在自己的电脑上安装 Node.js。
- 打开命令行，在命令行中进入到保存 `hello_world.js` 文件的目录，然后运行下面的命令：

```shell
node hello_world.js
```

确认命令行中输出了 `hello world`。

## 编程题

###### 一、给定圆的半径，求圆的面积

更改 `hello_world.js` 的代码，在控制台输出指定半径（可以固定写死）的圆的面积，输出结果要求保留两位小数。


