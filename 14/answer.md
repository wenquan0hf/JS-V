## 简答题

###### 一、参考答案
如果代码不受自己控制的时候，需要进行异常捕获，比如解析执行用户的输入脚本。

```js
try {
  // 'alert(111)' 可以是用户在输入框中输入的任意js脚本
  eval('alert(111)');
} catch(e) {
  // todo
}
```

###### 二、参考答案
stack 会记录程序的执行栈，对调试跟踪一些问题时非常有帮助。

###### 三、参考答案
`finally` 块的中代码始终都会执行，不管有没有异常发生。可以在错误发生时做一些降级处理，可以做一些清理工作，比如释放被脚本占用的资源，释放数据库联接等。

###### 四、参考答案
全局捕获，`window.onerror`

###### 五、参考答案
不需要，可以直接使用 `try...finally`

###### 六、参考答案
输出 `finally， 1`。因为 `finally`块中的代码始终会执行，`1` 是函数的返回值。

###### 七、参考答案
不会。因为 `try...catch` 只能处理同步代码。

###### 八、参考答案
不会。因为代码是语法错误，而 `try...catch` 只能处理运行时异常，语法错误在词法分析阶段就完成了。

## 编程题

###### 一、参考答案
```js
function convertToObject(str) {
  try {
    return JSON.parse(str);
  } catch (e) {
    console.log('使用 JSON.parse 异常，尝试使用 eval ' + e.message);
    try {
      return eval('(' + str + ')');
    } catch (e) {
      console.log('使用 eval 异常' + e.message);
    }
  }
}
```