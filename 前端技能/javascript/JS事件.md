 > 早期的前端交互,是由html与js的事件进行实现的

 ### 事件流

事件流指的是 从页面中接收事件的顺序；
现代浏览器标准DOM事件流的三阶段：

- 事件捕获
- 目标阶段
- 事件冒泡

所以有两个机会达到目标事件

### 事件获取的形式

- html元素内 `onclick="fn()"`
- js获取html元素，利用DOM1（不推荐）、DOM2的绑定事件函数

事件第一个默认参数为`event`对象

原生js开发不使用 html内联事件的主要原因
- 内联事件读取html属性，在用户修改后可能会出错
- 事件作用域在不同浏览器导致结果不同
- 耦合度高，不利于维护

> 之所以 推荐DOM2的绑定事件，是因为支持事件的解绑，尤其是在单页面时我们删除一个页面内组件时，希望可以解绑该组件内的事件。但需要注意点是，**匿名函数无法移除**，所以当你使用DOM2事件时，请不要使用匿名函数

**跨浏览器的事件**

跨浏览器事件主要是需要兼容老版本ie、火狐的事件标准，可以使用封装的`EventUtil`进行兼容。

 ### 事件对象与类型
事件函数默认参数是一个 `event`对象
dom节流中使用的是`event.target`


阻止特定事件的默认行为
```js
event.preventDefault()
// dom1使用
return false;
```
阻止事件冒泡或捕获
```js
event.stopPropagation()
```

> evenet 只有在事件处理执行期间，event对象才会存在，一旦事件处理程序执行完成，就会销毁

**事件的主要分类**

- UI事件  页面load、select，resize，scroll
- 焦点事件 blur、focus、focusout
- 鼠标事件 click/mousedown/mouseenter/mouseleave/mousemove/mouseout/mourseover/mourseup
- 滚轮事件 moursewheel
- 文本事件 keydown/keypress/keyup
- 键盘事件
- 合成事件 
- 变动事件dom变动事件
- 触摸与手势事件 touchstart/touchmove/touchend/touchend/touchcancel
手势： gesturestart/gesturechange/gestureend


 ### 高级事件


 ### 前沿事件应用，与CSS交互

### 事件冒泡和捕获的应用

### 事件的绑定与基础

### css对部分事件的分担

1、最基础的，鼠标hover事件
2、按钮禁用
3、长按事件
4、单次点击事件

[blog](https://segmentfault.com/a/1190000019342789)

 ### 总结