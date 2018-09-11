---
title: JavaScript Console
date: 2018-05-10 20:28:29
tags:
- JavaScript
- Console
categories:
- JavaScript
---

### JavaScript Console对象

<!--more-->

### 1. 方法

- [`Console.assert()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/assert)

  判断第一个参数是否为真，false的话抛出异常并且在控制台输出相应信息。

- [`Console.clear()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/clear)

  清空控制台。

- [`Console.count()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/count)

  以参数为标识记录调用的次数，调用时在控制台打印标识以及调用次数。

- [`Console.debug()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/debug)

  console.log方法的别称，使用方法可以参考**Console.log()**

- [`Console.dir()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/dir) 

  打印一条以三角形符号开头的语句，可以点击三角展开查看对象的属性。

- [`Console.dirxml()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/dirxml) 

  如果可以，打印 XML/HTML 元素表示的指定对象，或者 JavaScript 对象视图。

- [`Console.error()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/error)

  打印一条错误信息，使用方法可以参考 [string substitution](https://developer.mozilla.org/en-US/docs/Web/API/console#Using_string_substitutions)。

- [`Console._exception()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/_exception)  

  error方法的别称，使用方法参考 **Console.error()**

- [`Console.group()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/group)

  打印树状结构，配合groupCollapsed以及groupEnd方法;

- [`Console.groupCollapsed()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/groupCollapsed)

  创建一个新的内联 group。使用方法和group相同，不同的是groupCollapsed打印出来的内容默认是折叠的。

- [`Console.groupEnd()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/groupEnd)

  结束当前Tree

- [`Console.info()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/info)

  打印以感叹号字符开始的信息，使用方法和log相同

- [`Console.log()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/log)

  打印字符串，使用方法比较类似C的printf格式输出，可参考 [string substitution](https://developer.mozilla.org/en-US/docs/Web/API/console#Using_string_substitutions) 。

- [`Console.profile()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/profile)

  可以以第一个参数为标识，开始javascript执行过程的数据收集。和chrome控制台选项开Profiles比较类似，具体可参考[chrome profiles](http://www.oschina.net/translate/performance-optimisation-with-timeline-profiles)

- [`Console.profileEnd()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/profileEnd)

  配合profile方法，作为数据收集的结束。

- [`Console.table()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/table)

  将数据打印成表格。[Console.table [en-US\]](https://developer.mozilla.org/en-US/docs/Web/API/Console.table)

- [`Console.time()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/time)

  计时器，接受一个参数作为标识。

- [`Console.timeEnd()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/timeEnd)

  接受一个参数作为标识，结束特定的计时器。

- [`Console.timeStamp()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/timeStamp) 

  添加一个标记到浏览器的 [Timeline](https://developer.chrome.com/devtools/docs/timeline) 或 [Waterfall](https://developer.mozilla.org/en-US/docs/Tools/Performance/Waterfall) 工具.

- [`Console.trace()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/trace)

  打印[stack trace](https://developer.mozilla.org/en-US/docs/Web/API/console#Stack_traces).

- [`Console.warn()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/warn)

  打印一个警告信息，使用方法可以参考 [string substitution](https://developer.mozilla.org/en-US/docs/Web/API/console#Using_string_substitutions)。

### 2. 用法

> ### 0x01 输出文本到控制台

console对象中较多使用的主要有四个方法`console.log()`, `console.info()`, `console.warn()`, 和`console.error()`。他们都有特定的样式.

##### console 对象的静态方法

*`console.log`方法会自动在每次输出的结尾,添加换行符*

*`console.info`是`console.log`方法的别名,用法完全一样.只不过`console.info`方法会在输出信息的前面,加上一个蓝色图标*

*`console.debug`方法与`console.log`方法类似，会在控制台输出调试信息。但是，默认情况下，`console.debug`输出的信息不会显示，只有在打开显示级别在`verbose`的情况下，才会显示。*

*`warn`方法和`error`方法也是在控制台输出信息，它们与`log`方法的不同之处在于，`warn`方法输出信息时，在最前面加一个黄色三角，表示警告；`error`方法输出信息时，在最前面加一个红色的叉，表示出错。同时，还会高亮显示输出文字和错误发生的堆栈。其他方面都一样*

##### 打印单个对象

```javascript
var someObject = { str: "Some text", id: 5 };
console.log(someObject);
console.log(someObject.str);
console.log(someObject.id);
```

##### 打印多个对象

```javascript
var car = "Dodge Charger";
var someObject = {str:"Some text", id:5}; 
console.info("My first car was a", car, ". The object is: ", someObject);
```

##### 格式化打印

`%o`	        打印javascript对象，可以是整数、字符串以及JSON数据
`%d` or `%i`	打印整数
`%s`	        打印字符串
`%f`	        打印浮点数

```javascript
for (var i=0; i<5; i++) {

  console.log("Hello, %s. You've called me %d times.", "Bob", i+1);

}

console.log("I want to print a number:%d","string")
```

##### 为console定义样式

你可以使用`%c`为打印内容定义样式:

```javascript
console.log("%cMy stylish message", "color: red; font-style: italic");
```

**更多** <http://www.cnblogs.com/Wayou/p/chrome_dev_tool_style_console.html>

> ### 0x02 在控制台输出树状信息

```js
console.log("This is the outer level");
console.group();
console.log("Level 2");
console.group();
console.log("Level 3");
console.warn("More of level 3");
console.groupEnd();
console.log("Back to level 2");
console.groupEnd();
console.debug("Back to the outer level");
```



> ### 0x03 定时器

```js
console.time("answer time");
// alert("Click to continue");
console.timeEnd("answer time");
```



> ### 0x04 堆栈跟踪

**打印当前执行位置到console.trace()的路径信息**

```js
foo();

function foo() {
  function bar() {
    console.trace();
  }
  bar();
}
```

`Firefox`

![](https://ws4.sinaimg.cn/large/006tKfTcly1fr6i4jn6fjj310302dglr.jpg)

`Chrome`

![](https://ws1.sinaimg.cn/large/006tKfTcly1fr6i40msouj30pd02ht8r.jpg)

`Safari`

![](https://ws1.sinaimg.cn/large/006tKfTcly1fr6i4536cyj30b7024q2w.jpg)

`Term`

![](https://ws2.sinaimg.cn/large/006tKfTcly1fr6i4d5ck2j30m706g40o.jpg)



### more

<http://javascript.ruanyifeng.com/stdlib/console.html>